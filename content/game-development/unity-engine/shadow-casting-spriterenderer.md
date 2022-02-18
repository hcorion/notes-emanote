---
date: 2020-09-03T21:11
tags:
  - unity/shaders
  - unity/shadows
---

# Shadow-casting SpriteRenderer
[This thread](https://forum.unity.com/threads/why-cant-sprites-gameobjects-cast-shadows.215461/) Describes the approach to achieveing this.

This is what I used on a game for rendering shadows in their sprite-based cutouts.

Basically you need to create a material from the Standard material base instead of the default sprite material, then set the *Rendering Mode* in the Material to Cutout to prevent weird issues with alpha borders.

After that you'll want to attach a script similar to the one below to force the SpriteRenderer to cast shadows, since it's not exposed by default.

*Note: You can also just enter the inspector Debug mode and toggle it there, but the script is more designer/artist friendly.*

```csharp
[RequireComponent(typeof(SpriteRenderer))]
[ExecuteInEditMode]
public class ForceEnableShadows : MonoBehaviour
{
    private void OnEnable()
    {
        renderer = GetComponent<Renderer>();
        renderer.shadowCastingMode = UnityEngine.Rendering.ShadowCastingMode.On;
    }
}
```

If you do want to also enable double-sided rendering of the SpriteRenderer (so it casts shadows from both sides of the SpriteRenderer), you'll also want to add `Cull off` to the SubShader of a custom shader.
As an example:
```csharp
        SubShader
        {
            Tags { "RenderType" = "Opaque" "PerformanceChecks" = "False" }
            LOD 300
            Cull off
```
Here's a simple complete shader based on Unity's Mobile Diffuse:
```csharp
Shader "Custom/Simple3DSprite" {
	Properties{
		_MainTex("Base (RGB)", 2D) = "white" {}
	}
		SubShader{
			Tags { "RenderType" = "TransparentCutout" "Queue" = "AlphaTest" }
			LOD 150
			Cull off
			Blend One Zero
			ZWrite On
		CGPROGRAM
		#pragma surface surf Lambert noforwardadd
		sampler2D _MainTex;
		struct Input {
			float2 uv_MainTex;
		};
		void surf(Input IN, inout SurfaceOutput o) {
			fixed4 c = tex2D(_MainTex, IN.uv_MainTex);
			o.Albedo = c.rgb;
			o.Alpha = c.a;
			clip(o.Alpha-.2);
		}
		ENDCG
	}
		Fallback "Mobile/VertexLit"
}
```
---
date: 2020-09-04T00:58
tags:
    - math
    - unity
    - ue4
---

# Smoothly interpreting input

Sourced from [this reddit post](https://www.reddit.com/r/Unity3D/comments/bofmnl/adapting_lerp_time_to_smooth_out_input_noise_and/) which was taken from [this tweet](https://twitter.com/evil_arev/status/1128062338156900353?s=20).

![[lerping-input.mp4]]

It describes a way to get input and interpret it in a smooth fashion using some fancy math.

### Unity Code
```csharp
// Good noise smoothing, slow reaction to actual input
var a = Vector3.Lerp(a, b, 0.1f);
// Quick response to input, poor noise smoothing
var a = Vector3.Lerp(a, b, 0.9f);
// Adaptive Lerp
var a = Vector3.Lerp(a, b, k*(Mathf.Abs(a-b)));
```
### Unreal Engine Code
```cpp
// Good noise smoothing, slow reaction to actual input
auto a = FMath::Lerp(a, b, 0.1f);
// Quick response to input, poor noise smoothing
auto a = FMath::Lerp(a, b, 0.9f);
// Adaptive Lerp
auto a = FMath::Lerp(a, b, k*(FMath::Abs(a-b)));
```
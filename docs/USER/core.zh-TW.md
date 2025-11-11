# 核心概念

Let say for example, you have 5 power computers, And a project so big which require days to finish its works <br />
Such as 3D Rendering, or Video transcoding, or Large data sorting.

Sure, You can keep vertical scaling, until it's too expensive to do it. when you hit the critical point. <br />
You might considering horizontal scaling, which now you need a way to manage multiple computers

## 用 Blender 作爲範例

Let say there is a video file needs to export to mp4 file, video length is near 1 hour and the scene contain VFX or fluid computing

In this case you can seperate the render to multiple fragment, 5 mins per .mp4 file <br />
In the end, you output folder will contain multiple videos

During the renderering, you can tell multiple computers to render different timespan <br />
Then combine them in the end
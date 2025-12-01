# FFmpeg git master 分支编译版

基于 FFmpeg git master 分支的 Windows 编译版，包含 FFmpeg 的可执行程序 ffmpeg.exe，ffplay.exe 和 ffprobe.exe。git master 分支通常包含最新的错误修复和安全补丁。

FFmpeg 是一个广泛使用的跨平台多媒体框架，能够处理几乎所有常见和许多不常见的媒体格式，拥有超过1000个内部组件，并且可以利用数十种外部库来提供更多功能。

FFmpeg 提供了三种主要的工具，ffmpeg.exe 处理媒体文件，ffplay.exe 播放媒体文件，ffprobe.exe 查看媒体信息。 编译这些工具时，可以选择只支持部分组件和外部库。

## 本编译版

本编译版包含所有内部组件及以下外部库：

* 音频有关：libmp3lame（mp3 音频格式），libopus（opus 音频格式），librubberband（rubberband 音频滤镜）
* 视频有关：libx264（h264 视频格式），libx265（hevc 视频格式），libsvtav1（av1 视频格式编码），libdav1d（av1 视频格式解码），libvpx（vp8 和 vp9 视频格式），libwebp（webp 图片格式），libzimg（zscale 视频滤镜）
* 字幕有关：libass （ass/ssa 字幕），libfontconfig / libfreetype / libfribidi / libharfbuzz（字体处理）
* 渲染有关：sdl2（ffplay 渲染）
* 硬件加速：amf（AMD 硬件加速），libvpl （Intel 硬件加速），nvenc / nvdec / cuda / cuvid（nVidia 硬件加速），d3d11va / d3d12va / dxva2（DirectX 硬件加速），vulkan（GPU 硬件加速），mediafoundation（Windows Media Foundation 硬件加速，Windows 8+）

本编译版与 https://www.gyan.dev/ffmpeg/builds 的 git-essentials 版差异：

* 不支持 avisynth+ cairo libaom libgme libgsm libopencore-amrnb libopencore-amrwb libopenjpeg libopenmpt libspeex libsrt libssh libtheora libvidstab libvmaf libvo-amrwbenc libvorbis libxvid libzmq openal 等外部库
* 不支持 VAAPI 硬件加速
* 支持 libdav1d libsvtav1 两个 AV1 编解码库和 vulkan 硬件加速
* 采用动态链接

## 系统需求

* 支持 x86-64-v3 的 CPU，如 Intel 酷睿 4 代及以上，AMD 锐龙 1000 系列及以上（部分低功耗或嵌入式型号不满足 x86-64-v3 要求）
* Windows 7 及以上操作系统，ucrt 运行时

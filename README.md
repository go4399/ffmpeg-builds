# FFmpeg git master 分支编译版

基于 FFmpeg git master 分支的 Windows 编译版，包含 FFmpeg 的可执行程序 ffmpeg.exe，ffplay.exe 和 ffprobe.exe。git master 分支通常包含最新的错误修复和安全补丁。

FFmpeg 是一个广泛使用的跨平台多媒体框架，能够处理几乎所有常见和许多不常见的媒体格式，拥有超过1000个内部组件，并且可以利用数十种外部库来提供更多功能。

FFmpeg 提供了三种主要的工具，ffmpeg.exe 处理媒体文件，ffplay.exe 播放媒体文件，ffprobe.exe 查看媒体信息。 编译这些工具时，可以选择只支持部分组件和外部库。

## 本编译版

本编译版包含所有内部组件及以下外部库：
```
avisynth+ lcms2 libass libdav1d libfontconfig libfreetype libfribidi libharfbuzz
libmp3lame libopus libplacebo librubberband libshaderc libsoxr libsvtav1 libvorbis
libvpx libwebp libx264 libx265 libzimg mediafoundation sdl2 vapoursynth whisper
amf cuda_llvm cuvid d3d11va d3d12va dxva2 ffnvcodec libvpl nvdec nvenc vulkan
```

* 音频有关：libmp3lame（mp3 音频格式），libopus（opus 音频格式），libvorbis（vorbis 音频格式），librubberband（rubberband 音频滤镜），libsoxr（soxr 音频重采样），whisper.cpp（whisper 音频滤镜，使用 vulkan 加速）
* 视频有关：avisynth+ / vapoursynth（视频帧服务器和脚本处理），libx264（h264 视频格式），libx265（hevc 视频格式），libsvtav1（av1 视频格式编码），libdav1d（av1 视频格式解码），libvpx（vp8 和 vp9 视频格式），libwebp（webp 图片格式），lcms2（ICC 色彩管理），libplacebo（libplacebo 视频滤镜），libshaderc（vulkan 视频滤镜），libzimg（zscale 视频滤镜），cuda_llvm（cuda 视频滤镜）
* 字幕有关：libass（ass/ssa 字幕），libfontconfig / libfreetype / libfribidi / libharfbuzz（字体处理）
* 渲染有关：sdl2 / vulkan（ffplay 渲染）
* 硬件加速：amf（AMD 硬件加速），libvpl （Intel 硬件加速），nvenc / nvdec / cuda / cuvid（nVidia 硬件加速），d3d11va / d3d12va / dxva2（DirectX 硬件加速），vulkan（GPU 硬件加速），mediafoundation（Windows Media Foundation 硬件加速，Windows 8+）

本编译版与 https://www.gyan.dev/ffmpeg/builds 的 git-essentials 版差异：

* 不支持 cairo libaom libgme libgsm libopencore-amrnb libopencore-amrwb libopenjpeg libopenmpt libspeex libsrt libssh libtheora libvidstab libvmaf libvo-amrwbenc libxvid libzmq openal 外部库
* 不支持 vaapi 硬件加速
* 支持 lcms2 libdav1d libplacebo libshaderc libsoxr libsvtav1 vapoursynth whisper 外部库
* 支持 vulkan 硬件加速
* 采用动态链接

## 系统需求

* 支持 x86-64-v3 的 CPU，如 Intel 酷睿 4 代及以上，AMD 锐龙 1000 系列及以上（部分低功耗或嵌入式型号不满足 x86-64-v3 要求）
* Windows 7 及以上操作系统，ucrt 运行时

## 外部库版本

| libraries         | version               |
|-------------------|-----------------------|
| avisynth+         | 3.7.5-111-ge57b6869   |
| lcms2             | 2.18rc1-6-g23994d72   |
| libass            | 0.17.4-20-gcbb7432    |
| libdav1d          | 1.5.2-18-gbf82cfa7    |
| libfontconfig     | 2.17.1-114-g80e88952  |
| libfreetype       | 2.14.1                |
| libfribidi        | 1.0.16                |
| libharfbuzz       | 12.2.0                |
| libmp3lame        | 3.100                 |
| libopus           | 1.6-13-g27d984b1      |
| libplacebo        | 7.351.0-106-gbc90ef94 |
| librubberband     | 4.0.0-2-ge4296ac      |
| libshaderc        | 2025.5-1-ge0a5092     |
| libsoxr           | 0.1.3                 |
| libsvtav1         | 3.1.2                 |
| libvorbis         | 1.3.7                 |
| libvpx            | 1.15.2                |
| libwebp           | 1.6.0                 |
| libx264           | 0.165.3223-g0480cb05  |
| libx265           | 4.1-212-g9e551a99     |
| libzimg           | 3.0.6                 |
| sdl2              | 2.32.0-145-g3eba0b6f8 |
| vapoursynth       | R73                   |
| whisper.cpp       | 1.8.2-345-g6114e692   |
| amf-headers       | 1.5.0                 |
| ffnvcodec-headers | 13.0.19.0             |
| libvpl            | 2.16.0                |
| vulkan-headers    | 1.4.335.0             |

## 更新

2025-12-25
* 修复 avcodec-62.dll avfilter-11.dll ffplay.exe 导出外部库函数的问题
* 添加 vulkan-1.dll doc ffpresets README.txt GPLv2.txt

2025-12-22
* 增加 libsoxr

2025-12-15
* 增加 whisper.cpp 的 vulkan 后端

2025-12-13
* 增加 whisper.cpp cuda_llvm

2025-12-09
* 增加 avisynth+ lcms2 libplacebo libshaderc libvorbis vapoursynth vulkan

2025-12-01
* 开始

## Last Source

https://github.com/FFmpeg/FFmpeg/commit/abb15241388c18d1d2587dd8eb06f5eb50e2ff6a



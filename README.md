# FFmpeg git master 分支编译版

基于 FFmpeg git master 分支的 Windows 编译版，包含 FFmpeg 的可执行程序 ffmpeg.exe，ffplay.exe 和 ffprobe.exe。git master 分支通常包含最新的错误修复和安全补丁。

FFmpeg 是一个广泛使用的跨平台多媒体框架，能够处理几乎所有常见和许多不常见的媒体格式，拥有超过1000个内部组件，并且可以利用数十种外部库来提供更多功能。

FFmpeg 提供了三种主要的工具，ffmpeg.exe 处理媒体文件，ffplay.exe 播放媒体文件，ffprobe.exe 查看媒体信息。 编译这些工具时，可按需选取内部组件和外部库进行构建。

## 本编译版的配置

本编译版启用了全部内部组件，并链接了以下外部库：
```
avisynth+ lcms2 libaom libass libdav1d libfontconfig libfreetype libfribidi libharfbuzz
libjxl libmp3lame libopus libplacebo librubberband libshaderc libsoxr libsvtav1 libvorbis
libvpx libwebp libx264 libx265 libzimg mediafoundation sdl2 vapoursynth whisper
amf cuda_llvm cuvid d3d11va d3d12va dxva2 ffnvcodec libvpl nvdec nvenc vulkan
```

* 音频有关：libmp3lame（mp3 音频格式编码），libopus（opus 音频格式），libvorbis（vorbis 音频格式），librubberband（rubberband 音频滤镜），libsoxr（soxr 音频重采样），whisper.cpp（whisper 音频滤镜，使用 vulkan 加速）
* 视频有关：avisynth+ / vapoursynth（视频帧服务器和脚本处理），libaom（av1 视频格式 / avif 图片格式），libx264（h264 视频格式编码），libx265（hevc 视频格式编码），libsvtav1（av1 视频格式编码），libdav1d（av1 视频格式解码），libvpx（vp8 和 vp9 视频格式），libjxl（jxl 图片格式），libwebp（webp 图片格式编码），lcms2（ICC 色彩管理），libplacebo（libplacebo 视频滤镜），libshaderc（vulkan 视频滤镜），libzimg（zscale 视频滤镜），cuda_llvm（cuda 视频滤镜）
* 字幕有关：libass（ass/ssa 字幕），libfontconfig / libfreetype / libfribidi / libharfbuzz（字体处理）
* 渲染有关：sdl2 / vulkan（ffplay 渲染）
* 硬件加速：amf（AMD 硬件加速），libvpl （Intel 硬件加速），nvenc / nvdec / cuda / cuvid（nVidia 硬件加速），d3d11va / d3d12va / dxva2（DirectX 硬件加速），vulkan（GPU 硬件加速），mediafoundation（Windows Media Foundation 硬件加速，Windows 8+）

本编译版与 https://www.gyan.dev/ffmpeg/builds 的 git-essentials 版的差异：

* 未包含 cairo libgme libgsm libopencore-amrnb libopencore-amrwb libopenjpeg libopenmpt libspeex libsrt libssh libtheora libvidstab libvmaf libvo-amrwbenc libxvid libzmq openal 外部库
* 未包含 vaapi 硬件加速
* 包含 lcms2 libdav1d libjxl libplacebo libshaderc libsoxr libsvtav1 vapoursynth whisper 外部库
* 包含 vulkan 硬件加速
* 编译为动态链接库

## 系统需求

* 处理器必须支持 x86-64-v3（AVX2）指令集，例如 Intel 酷睿 4 代及以上，或 AMD 锐龙 1000 系列及以上（部分低功耗或嵌入式型号不支持 AVX2 指令）
* 操作系统需为 Windows 10 或更高版本

## FFmpeg 版本信息

Version: 8.2-dev.1712+260612 (n8.2-dev-1712-g2cc7b87b)

Source: https://github.com/FFmpeg/FFmpeg/commit/2cc7b87bdb75bcb59bf8bcd5296ca43f89b3a909

License: GPL version 2 or later

## 外部库版本

| libraries         | version                     |
|-------------------|-----------------------------|
| avisynth+         | 3.7.5-316-g345a00034        |
| lcms2             | 2.19.1-13-g1984ae8e0        |
| libaom            | 3.14.1                      |
| libass            | 0.17.4-29-gc425f6d7e        |
| libdav1d          | 1.5.3-54-ge9c5800ac         |
| libfontconfig     | 2.18.1-16-gee5ee3101        |
| libfreetype       | 2.14.3-59-g25a08f24c        |
| libfribidi        | 1.0.16-5-g069a7e3d3         |
| libharfbuzz       | 14.2.1-12-ge113622a9        |
| libjxl            | 0.11.2                      |
| libmp3lame        | 3.100                       |
| libopus           | 1.6.1-20-gf18e26e64         |
| libplacebo        | 7.360.0-81-g2d0979fb5       |
| librubberband     | 4.0.0-2-ge4296ac80          |
| libshaderc        | 2026.2                      |
| libsoxr           | 0.1.3                       |
| libsvtav1         | 4.1.0-193-g349f4eb9c        |
| libvorbis         | 1.3.7-36-ge3c9861ff         |
| libvpx            | 1.16.0-150-g41e48324d       |
| libwebp           | 1.6.0-187-gb43b2caa7        |
| libx264           | 0.165.3223-g0480cb05        |
| libx265           | 4.2-40-g6fdfffe8d           |
| libzimg           | 3.0.6-218-gfa52dee9e        |
| sdl2              | 2.32.10-88-g2e5b9a860       |
| vapoursynth       | R76                         |
| whisper.cpp       | 1.8.6-58-gdf7638d82         |
| amf-headers       | 1.5.2                       |
| ffnvcodec-headers | 13.0.19.0                   |
| libvpl            | 2.16.0                      |
| vulkan-headers    | 1.4.350                     |
| vulkan-loader     | 1.4.350                     |

## 更新记录

2026-06-04
* 使用 clang version 22.1.7 编译
* fontconfig 更新至 v2.18.1
* harfbuzz 更新至 v14.2.1

2026-06-01
* libplacebo 更新至 v7.365.0
* whisper.cpp 更新至 v1.8.6
* amf-headers 更新至 v1.5.2

2026-05-28
* libaom 更新至 v3.14.1
* whisper.cpp 更新至 v1.8.5

2026-05-24
* fontconfig 更新至 v2.18.0

2026-05-16
* libaom 更新至 v3.14.0
* sdl2 更新至 2.32.10
* vapoursynth 更新至 R76

2026-05-08
* glslang 更新至 v16.3.0
* lcms2 更新至 v2.19.1
* shaderc 更新至 v2026.2
* spirv-tools 更新至 v2026.2.rc2
* vulkan-headers vulkan-loader 更新至 v1.4.350

2026-05-05
* libplacebo 更新至 v7.364.0

2026-05-01
* libplacebo 更新至 v7.363.0

2026-04-24
* 使用 clang version 22.1.4 编译
* lcms2 更新至 v2.19
* vapoursynth 更新至 R74

2026-04-20
* harfbuzz 更新至 v14.2.0
* lcms2 更新至 v2.19rc1

2026-04-19
* libx265 更新至 v4.2

2026-04-05
* libaom 更新至 v3.13.3
* harfbuzz 更新至 v14.1.0

2026-04-02
* harfbuzz 更新至 v14.0.0

2026-03-28
* 使用 clang version 22.1.2 编译

2026-03-24
* freetype 更新至 v2.14.3
* svt-av1 更新至 v4.1.0

2026-03-20
* harfbuzz 更新至 v13.2.1

2026-03-19
* harfbuzz 更新至 v13.2.0
* whisper.cpp 更新至 v1.8.4

2026-03-17
* ffmpeg 版本基线切换至 n8.2-dev

2026-03-16
* harfbuzz 更新至 v13.1.1

2026-03-12
* harfbuzz 更新至 v13.1.0

2026-03-09
* harfbuzz 更新至 v13.0.1
* libplacebo 更新至 v7.362.0

2026-03-04
* freetype 更新至 v2.14.2
* libplacebo 更新至 v7.361.0

2026-02-26
* 移除 libsrt

2026-02-16
* librubberband 改为静态链接

2026-02-12
* libjxl 更新至 v0.11.2
* libplacebo 更新至 v7.360.0
* libvpx 更新至 v1.16.0
* spirv-tools 更新至 v2026.1
* svt-av1 更新至 v4.0.1

2026-01-26
* glslang 更新至 v16.2.0
* harfbuzz 更新至 v12.3.2
* libvpx 更新至 v1.16.0-rc1
* shaderc 更新至 v2026.1
* spirv-tools 更新至 v2026.1.rc1
* svt-av1 更新至 v4.0.0
* vulkan-headers vulkan-loader 更新至 v1.4.341

2026-01-21
* 使用 clang version 21.1.8 编译
* whisper 滤镜使用 CPU 推理时，字幕生成速度明显提升

2026-01-16
* whisper.cpp 更新至 v1.8.3
* vulkan-headers vulkan-loader spirv-headers spirv-tools glslang shaderc 更新至 vulkan-tmp-1.4.338

2026-01-11
* 取消 libplacebo librubberband libshaderc 的延迟加载

2026-01-06
* 编译 librubberband 时，将默认的重采样后端由 libsamplerate 替换为 libsoxr-lsr

2025-12-31
* 增加 libaom libjxl 以支持 avif jxl 图像格式
* 增加 libsrt
* 增加 mpv 播放器（需解压缩到 ffmpeg 目录里运行）
* ~~将 libplacebo librubberband libshaderc 编译为延迟加载动态库~~

2025-12-25
* 修复 avcodec-62.dll avfilter-11.dll ffplay.exe 对外部库函数的错误导出
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
* 初始构建


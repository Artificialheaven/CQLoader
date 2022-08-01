# 参数构成
  参数类似一行代码，由 程序名(参数11参数2,参数3) 组成，末尾无须也不能带有 ; 。不需要带 "" 、 转义符 \ 等等。
  例如 onebot({"action":"get_login_info","params":{}})
  或 runtime(rundir) 等。
# 程序
  ## onebot
    + 该指令只有一个参数，参数为向 go-cqhttp 直接发送的json，返回 go-cqhttp 返回的数据。一般来说为插件可以直接使用的编码。
  ## runtime
   + 可能的参数
    - rundir 获取当前星辰框架运行的真实目录。在框架一般运行状态下，也是 go-cqhttp.exe 运行的目录。
    - version 获取当前 CQLoader 的版本。
    - CPUInfo 获取当前CPU的数据，共两行，分别为 cpu型号、cpu占用情况。
  ## cq
   ### 可能的参数
    1. Fimage
     - 这个参数为图片的绝对路径，返回可用的图片CQ码。
    2. Uimage
     - 这个参数为网络图片的链接，下载后返回图片CQ码。（你也可以手动构建符合 go-cqhttp 标准的CQ码来进行发送，并不一定需要使用本命令）。
    3. voice
     - 这个参数为语音的绝对路径，可以是amr或silk等 go-cqhttp 可直接识别的音频文件。除非装载了 ffmpeg 否则不能发送mp3等音频文件。
    4. Avoice
     - 这个参数由 kt.p32mr 返回，是音频文件在 data/voices/ 下的文件名。返回go-cqhttp的语音CQ码。
  ## kt
   ### 可能的参数
    1. p32mr
     - 这个参数为mp3文件的相对路径，将文件转换为amr文件，并返回amr文件的相对路径。（路径在 /data/voices/ 内，一般只返回文件名）
     - 这个参数为amr的码率，为空则默认8000。（码率越高，文件越大，上传时间越长）
      

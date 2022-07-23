# 参数构成
  参数由多个小节组成，每个小节之间由 __&andOtherInfo&__ 分割。
  例如 onebot&andOtherInfo&{"action":"get_login_info","params":{}}
# 小节
  此后，我们将第一个小节命名为指令，其余命名为参数。
  ## onebot
-      该指令只有一个参数，参数为向 go-cqhttp 直接发送的json，返回 go-cqhttp 返回的数据。一般来说为插件可以直接使用的编码。
  ## runtime
      rundir 获取当前星辰框架运行的真实目录。在框架一般运行状态下，也是 go-cqhttp.exe 运行的目录。
      version 获取当前 CQLoader 的版本。
      CPUInfo 获取当前CPU的数据，共两行，分别为 cpu型号、cpu占用情况。
  ## cq
      Fimage
          - 这个参数为图片的绝对路径，返回可用的图片CQ码。
      Uimage
          - 这个参数为网络图片的链接，下载后返回图片CQ码。（你也可以手动构建符合 go-cqhttp 标准的CQ码来进行发送，并不一定需要使用本命令）。
      voice
          - 这个参数为语音的绝对路径，可以是amr或silk等 go-cqhttp 可直接识别的音频文件。除非装载了 ffmpeg 否则不能发送mp3等音频文件。
  ## kt
      p32mr
          - 这个参数为mp3文件的绝对路径，将文件转换为amr文件，并返回amr文件的绝对路径。
          - 这个参数为amr的码率，为空则默认8000。（码率越高，文件越大，上传时间越长）
      

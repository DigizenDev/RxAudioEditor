# RxAudioEditor - 音频处理 - google 官方兼容到7.x

# 剪切mp3 使用

'''java
    String outPath = makeRingtoneFilename(title, ".mp3");
    if (outPath == null) {
        Runnable runnable = new Runnable() {
            public void run() {
                showFinalAlert(new Exception(), R.string.no_unique_filename);
            }
        };
        mHandler.post(runnable);
        return;
    }
    File outFile = new File(outPath);
    try {
        // 创建新文件
        mSoundFile.WriteFile(outFile,  startFrame, endFrame - startFrame);
    } catch (Exception e) {
        if (outFile.exists()) {
            outFile.delete();
        }
        e.printStackTrace();
    }
'''
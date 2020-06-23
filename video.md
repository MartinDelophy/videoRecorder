实现该方式主要的api：
[getDisplayMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia)
[MediaRecorder](https://developer.mozilla.org/zh-CN/docs/Web/API/MediaRecorder/MediaRecorder)

主要流程:
```flow
st=>start: 开始
e=>end: 实现桌面视频录制
io1=>inputoutput: 获取调用权限
cond=>condition: 用户同意
sub1=>subroutine: 获取桌面流
sub2=>subroutine: 录制操作
cond2=>condition: 是否保存
sub3=>subroutine: 下载视频



st->io1->cond->sub1->sub2->cond2
cond(yes,right)->sub1
cond(no)->io1(e)
cond2(yes,right)->sub3->e
cond2(no)->e

```
几个重要的知识点：
1.非编码帧
2.编码帧
3.window.URL.createObjectURL 为什么要用这个来设定到video的URL上

关于一些变革
用 srcObject 来代替src


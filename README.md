
# Android-AlertView


## Demo
![](https://github.com/saiwu-bigkoo/Android-AlertView/blob/master/preview/alertviewdemo.gif)

```java
   compile 'com.bigkoo:alertview:1.0.3'
```

### config in java code
```java
new AlertView("上传头像", null, "取消", null,
                new String[]{"拍照", "从相册中选择"},
                this, AlertView.Style.ActionSheet, new OnItemClickListener(){
                    public void onItemClick(Object o,int position){
                        Toast.makeText(this, "点击了第" + position + "个", 
                        Toast.LENGTH_SHORT).show();
                    }
                }).show();
                
//或者builder模式创建
new AlertView.Builder().setContext(context)
                .setStyle(AlertView.Style.ActionSheet)
                .setTitle("选择操作")
                .setMessage(null)
                .setCancelText("取消")
                .setDestructive("拍照", "从相册中选择")
                .setOthers(null)
                .setOnItemClickListener(listener)
                .build()
                .show();
```
```java
new AlertView("标题", "内容", null, new String[]{"确定"}, null, this, 
                AlertView.Style.Alert, null).show();


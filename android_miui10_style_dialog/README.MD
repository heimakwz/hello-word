# Android MIUI10 Style Dialog

---

#### **MIUI10样式Dialog已经封装到CommonUI仓库里，以下是Dialog的封装使用.**

![](/android_miui10_style_dialog/assets/miui10.png)

### 一、Common-Alert-Dialog（一般告警弹窗）

```
private void deleteConfirmDialog() {
        CommonAlertDialog alertDialog = new CommonAlertDialog.Builder(activity())
                .title("title")
                .content("content")
                .leftStr(R.string.Cancel, (dialog1, view) -> dialog1.dismiss())
                .rightStr(R.string.OK, (dialog12, view) -> {
                   //TODO
                })
                .rightTextColor(R.color.black)
                .build();
        alertDialog.show();
    }
```

**Example:**![](/android_miui10_style_dialog/assets/alert1.jpg)![](/android_miui10_style_dialog/assets/alert2.jpg)

```
private void showGotItDialog(String msg) {
        CommonAlertDialog gotItDialog = new CommonAlertDialog.Builder(activity())
                .content(msg)
                .okStr(R.string.got_it, (dialog, view1) -> {
                    dialog.dismiss();
                })
                .build();
        gotItDialog.show();
    }
```

![](/android_miui10_style_dialog/assets/alert3.jpg)

### 二、Common-Bottom-Loading-Dialog（底部加载弹窗）

```
private void showLoadingDialog() {
        CommonBottomLoadingDialog syncDialog = new CommonBottomLoadingDialog.Builder(activity())
                .message(R.string.usermanage_synchronizing_please_later)
                .cancelable(false)
                .build();
        syncDialog.show();
        //取消loading
        syncDialog.setOnDismissListener(dialog -> {
            //TODO
        });
    }
```

![](/android_miui10_style_dialog/assets/loading.jpg)

### 三、Common-Bottom-Select-Dialog（底部选择弹窗）

```
private void showSelectDialog() {
        CommonBottomSelectDialog selectDialog = new CommonBottomSelectDialog.Builder(activity())
                .title("title")
                .select1Str(R.string.usermanage__change_authority, dialog -> {
                   //TODO
                    dialog.dismiss();
                })
                .select2Str(R.string.delete, dialog -> {
                    //TODO
                    dialog.dismiss();
                })
                .build();
        selectDialog.show();
```

![](/android_miui10_style_dialog/assets/select1.jpg)![](/android_miui10_style_dialog/assets/select2.jpg)

### 四、Common-Named-Dialog\(命名和重命名弹窗\)

```
 protected void showNameDialog() {
        CommonNamedDialog editTextDialog = new CommonNamedDialog.Builder(this)
                .title(R.string.rename)
                .input(mSelectLockUserInfo.getName())
                .leftStr(R.string.Cancel)
                .rightStr(R.string.OK, (dialog, view, input) -> {
                    //TODO
                    dialog.dismiss();
                })
                .build();
        editTextDialog.show();
    }
```

![](/android_miui10_style_dialog/assets/name1.jpg)![](/android_miui10_style_dialog/assets/name2.jpg)


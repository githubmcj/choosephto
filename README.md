ChoosePhoto
====
### 1、[功能描述]：
##### 主要用于头像修改、单张图片选择上传


### 2、[项目结构简介]：
##### （1）example为demo,里面主要包括使用方式，如何调用；
##### （2）library为依赖Module，第三方库引用的文件都在library文件夹里
##### （3）其他文件默认提交，不做说明


### 3、[测试DEMO]：
##### 调用选择图片代码如下
    Intent intent = new Intent(MainActivity.this, DialogPhotoForCutActivity.class);
                    intent.putExtra("filePath", getPath(MainActivity.this));
                    startActivityForResult(intent, TAKE_PHOTO);
##### 获取图片路径回调代码如下
        @Override<br>
        public void onActivityResult(int requestCode, int resultCode, Intent data) {
            if (resultCode == Activity.RESULT_OK) switch (requestCode) {
                case TAKE_PHOTO:
                    if (null != data) {
                        String imageName = data.getStringExtra("imageName");
                        tv_path.setText(imageName);
                        Bitmap bm = BitmapFactory.decodeFile(imageName);
                        // 将图片显示到ImageView中
                        avatar.setImageBitmap(bm);
                   }
                   break;
            }
              super.onActivityResult(requestCode, resultCode, data);
        }


### 4、[历史版本]：
##### 2018.6.28<br>
    *完成图片选择功能，其中包括有无切图功能，版本v1.0.0
    *引用方式：   
    allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
    dependencies {
	        implementation 'com.github.githubmcj:choosephoto:v1.0.0'
	}


### 5、[联系方式]：
##### email：550612711@qq.com 对这个工程不明白的地方可以通过该联系方式与我联系。

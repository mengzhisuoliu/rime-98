## Mac 效果图
- 这是应用皮肤后的输入效果：
![image](https://raw.githubusercontent.com/thep0y/rime-98/master/images/default.png)
- 这是反查的效果：
![image](https://raw.githubusercontent.com/thep0y/rime-98/master/images/reverse.png)

皮肤是在squirrel.yaml里，名叫“mojave_dark”，配置可参考本仓库/build/squirrel.yaml。

## windows10 效果图
### 1、green_dark
![green dark](https://github.com/thep0y/rime-98/raw/master/images/green_dark.png)
### 2、red_dark
![red dark](https://github.com/thep0y/rime-98/raw/master/images/red_dark.png)
### 3、orange_dark
![orange dark](https://github.com/thep0y/rime-98/raw/master/images/orange_dark.png)
### 4、win10_black
![win10 black](https://github.com/thep0y/rime-98/raw/master/images/win10_black.png)



**F4 键在五笔词库和单字词库之间切换。**



## 词库/码表

词库文件在`dist`目录中。

```
├── default.custom.yaml # 配置文件
├── pinyin_simp.dict.yaml # 拼音词库
├── pinyin_simp.schema.yaml # 拼音词库配置
├── wubi98.dict.yaml # 98含词词库
├── wubi98.schema.yaml # 98含词词库配置
├── wubi98single.dict.yaml # 98单字词库
├── wubi-98-single-gbk.dict.yaml # 98单字词库配置
├── wubi-98-single-gbk.schema.yaml # 98常用单字词库
└── wubi98single.schema.yaml # 98常用单字词库配置
```

## 使用

### 鼠须管(Mac)使用简要步骤：

- 将词库文件下载下来后，放在RIME的配置文件夹内。
- 配置文件夹为`~/Library/Rime`，快速进入方式是通过RIME的“用户设定...”进入。
- 复制`squirrel.custom.yaml`到词库同目录中。
- 选择“重新部署”，即可生效。

### 小狼毫(Windows)使用简要步骤：
- 右击任务栏的小狼毫输入法图标，打开“用户文件夹”。
- 将词库下载下来放进此文件夹。
- 右击任务栏的小狼毫输入法图标，点击“重新部署”，应该就能用了。如果不能用的话，在“输入法设定”里找找是不是有“五笔98”，如果没有，检查你之前的操作。

### 中州韵(Linux)的使用

仅以fcitx-rime为例，ibus-rime有兼容问题：

#### (1)Debian系

Ubuntu、Debian、Mint等基于Debian的系统都用此方式安装。
```shell
sudo apt autoremove fcitx  # 先卸载掉可能内置的fcitx，一般内置的输入法都会装很多冗余的东西，实际上用不到
sudo apt install fcitx-rime  # 安装fcitx-rime时会自动安装必需依赖，但输入法配置(如fcitx-configtool)需单独安装
```
Ubuntu和Mint都有单独的输入法管理设置，只需要将输入法换成fcitx，并注销即可成功切换成fcitx。
码表的位置在`~/.config/fcitx/rime`下，可将rime目录下的所有文件都删除，也可以不删，然后将本仓库根目录里的七个yaml文件放到rime目录下，右击工具栏的输入法图标，选择`重新部署`，最后再选择中州韵，即可开启98输入之旅了。
> debian系也可以使用fcitx5，只是需要自行编绎，建议有动手能力的人自行编绎。使用fcitx5的话，可以在我的另一个仓库里[配置皮肤](https://github.com/thep0y/fcitx5-themes)。
#### (2)Arch系：

Manjaro等基于arch的系统以此方式安装。
```shell
# 安装输入法和配置管理软件
sudo pacman -S fcitx-rime fcitx-configtool
# 写入输入法环境变量
echo 'export GTK_IM_MODULE=fcitx\nexport QT_IM_MODULE=fcitx\nexport XMODIFIERS=@im=fcitx' > .xprofile
```
注销即可用。码表导入同Debian。
**Arch**最好还是安装fcitx5-rime，体验更好，我用的就是，使用fcitx5的话，可以在我的另一个仓库里[配置皮肤](https://github.com/thep0y/fcitx5-themes)。


## 补充一点：
我用的wubi98.dict.yaml内的码表内的词库只有两个元素，其实默认是三个元素，最后应该有个词频，但是我觉得用五笔打字并不需要词频调整，所以就没有将词频部分写上。

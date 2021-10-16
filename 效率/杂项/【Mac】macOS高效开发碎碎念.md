## 零、前言

遇到就记录。

## 一、如何在macOS的Finder中快速新建txt文件？
 - 我们知道，在windows中，右键鼠标就可以选择新建txt文件，十分方便，那么我们如何在macOS中实现呢？
 - 其实方法还是有很多的，但是这里我们介绍一种我个人比较喜欢使用的：
### 解决方案：通过 Automator 创建服务
 - 利用 macOS 自带的 Automator，我们可以将「新建文本文件」这一动作添加至 Finder 的「服务」菜单中，便于随时调用
 - 步骤：
  1. 首先，打开 Automator 并创建一个新文稿，类型选择「服务」。
  2. 随后，在 Automator 上方将输入类型设置为「没有输入」，并选择应用程序为「Finder」。
  3. 接着，从左侧资源库的「实用工具」分类中将「运行 AppleScript」操作拖拽至右侧的动作区，在其中粘贴以下代码并保存。
  ```AppleScript
  on run {input, parameters}

    tell application "Finder"
    set selection to make new file at (get insertion location)
    end tell

    return input
  end run
  ```
  4. 这时，你应该就能在 Finder 的「服务」菜单中找到「新建文本文件」这一操作了。只需要点击运行服务，就可以在当前位置创建一个新文本文件。
  5. 此外，你还可以在「系统偏好设置-键盘-快捷键」中为该操作添加自定义快捷键，让创建文件更简单。

## 二、mac系统如何修改默认打开方式

- 在mac中打开文件时，系统总会有默认的推荐打开工具，那么如果有不合我们心意的默认打开工具，我们如何去修改呢？

### 解决方案：

  很简单，右击该文件，选择「显示简介」，然后在打开方式一栏进行修改。

## *、参考链接
一、《4 种方法，让你在 macOS 上快速新建 txt 文本文件》； https://sspai.com/post/41867

二、《mac系统如何修改默认打开方式》；http://blog.itpub.net/69957697/viewspace-2726134/

虽然有错误，但是可以保存正确的合并后的文件，并 add 到缓存中。

在编辑窗口中修改完，保存时，控制台输出下面的错误：

wangxiangfx@wangxiangfx MINGW64 /d/work/beside (master|MERGING)
$ git mergetool -t meld
Merging:
src/com/feinno/beside/application/BesideInitUtil.java

Normal merge conflict for 'src/com/feinno/beside/application/BesideInitUtil.java':
  {local}: modified file
  {remote}: modified file

(Meld.exe:4144): Gdk-CRITICAL **: gdk_device_get_source: assertion 'GDK_IS_DEVICE (device)' failed

(Meld.exe:4144): Gdk-CRITICAL **: gdk_device_get_source: assertion 'GDK_IS_DEVICE (device)' failed

(Meld.exe:4144): Gdk-CRITICAL **: gdk_device_get_source: assertion 'GDK_IS_DEVICE (device)' failed

(Meld.exe:4144): Gdk-CRITICAL **: gdk_device_get_source: assertion 'GDK_IS_DEVICE (device)' failed


21:59 2018/4/17 

设置完成后，调用，出下面的错误。

wangxiang@DESKTOP-CLJVRPH MINGW64 /c/doc (master|REBASE 1/1)
$ git mergetool
Merging:
date/4.15.txt

Normal merge conflict for 'date/4.15.txt':
  {local}: modified file
  {remote}: modified file

(meld.exe:14360): Pango-CRITICAL **: pango_win32_font_logfont: assertion 'PANGO_WIN32_IS_FONT (font)' failed

然后查看状态

wangxiang@DESKTOP-CLJVRPH MINGW64 /c/doc (master|REBASE 1/1)
$ git status
rebase in progress; onto fde133f
You are currently rebasing branch 'master' on 'fde133f'.
  (all conflicts fixed: run "git rebase --continue")

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   date/4.15.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        date/4.15_BACKUP_14128.txt
        date/4.15_BASE_14128.txt
        date/4.15_LOCAL_14128.txt
        date/4.15_REMOTE_14128.txt

已经设置，不保存备份文件：
mergetool.keepbackup=false
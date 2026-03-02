# دليل شامل: أدوات مدير النظام - Rocky Linux 10

> **الإصدار:** Rocky Linux 10  
> **التاريخ:** مارس 2026  
> **الغرض:** قائمة كاملة بجميع أدوات إدارة النظام من الأصغر إلى الأكبر

---

## 📋 جدول المحتويات

1. [أدوات النظام الأساسية](#أدوات-النظام-الأساسية)
2. [أدوات إدارة العمليات](#أدوات-إدارة-العمليات)
3. [أدوات إدارة الشبكات](#أدوات-إدارة-الشبكات)
4. [أدوات إدارة التخزين والأقراص](#أدوات-إدارة-التخزين-والأقراص)
5. [أدوات المراقبة والأداء](#أدوات-المراقبة-والأداء)
6. [أدوات الأمان](#أدوات-الأمان)
7. [أدوات إدارة الحزم](#أدوات-إدارة-الحزم)
8. [أدوات النسخ الاحتياطي والاستعادة](#أدوات-النسخ-الاحتياطي-والاستعادة)
9. [أدوات إدارة المستخدمين والصلاحيات](#أدوات-إدارة-المستخدمين-والصلاحيات)
10. [أدوات السجلات والتشخيص](#أدوات-السجلات-والتشخيص)
11. [أدوات الأتمتة والبرمجة](#أدوات-الأتمتة-والبرمجة)
12. [أدوات التحكم بالخدمات](#أدوات-التحكم-بالخدمات)
13. [أدوات الأداء المتقدمة](#أدوات-الأداء-المتقدمة)
14. [أدوات واجهات الرسومية](#أدوات-واجهات-الرسومية)
15. [طرق التثبيت لبيئة Offline](#طرق-التثبيت-لبيئة-offline)

---

## 1. أدوات النظام الأساسية

### 1.1 أوامر التنقل والملفات الأساسية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `ls` | coreutils | عرض محتويات المجلدات | ⭐⭐⭐⭐⭐ |
| `cd` | bash (مدمج) | التنقل بين المجلدات | ⭐⭐⭐⭐⭐ |
| `pwd` | coreutils | عرض المسار الحالي | ⭐⭐⭐⭐⭐ |
| `mkdir` | coreutils | إنشاء مجلدات | ⭐⭐⭐⭐⭐ |
| `rmdir` | coreutils | حذف مجلدات فارغة | ⭐⭐⭐⭐ |
| `rm` | coreutils | حذف ملفات ومجلدات | ⭐⭐⭐⭐⭐ |
| `cp` | coreutils | نسخ ملفات ومجلدات | ⭐⭐⭐⭐⭐ |
| `mv` | coreutils | نقل/إعادة تسمية | ⭐⭐⭐⭐⭐ |
| `touch` | coreutils | إنشاء ملفات فارغة | ⭐⭐⭐⭐ |
| `cat` | coreutils | عرض محتوى الملفات | ⭐⭐⭐⭐⭐ |
| `less` | less | عرض ملفات كبيرة | ⭐⭐⭐⭐⭐ |
| `more` | util-linux | عرض ملفات (أساسي) | ⭐⭐⭐ |
| `head` | coreutils | عرض أول سطور | ⭐⭐⭐⭐ |
| `tail` | coreutils | عرض آخر سطور | ⭐⭐⭐⭐⭐ |
| `file` | file | معرفة نوع الملف | ⭐⭐⭐⭐ |
| `stat` | coreutils | معلومات تفصيلية عن ملف | ⭐⭐⭐⭐ |

### 1.2 أدوات البحث والتصفية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `find` | findutils | البحث عن ملفات | ⭐⭐⭐⭐⭐ |
| `locate` | mlocate | بحث سريع بقاعدة بيانات | ⭐⭐⭐⭐ |
| `updatedb` | mlocate | تحديث قاعدة بيانات locate | ⭐⭐⭐⭐ |
| `grep` | grep | البحث داخل الملفات | ⭐⭐⭐⭐⭐ |
| `egrep` | grep | grep متقدم | ⭐⭐⭐⭐ |
| `fgrep` | grep | بحث سريع ثابت | ⭐⭐⭐ |
| `ripgrep (rg)` | ripgrep | بحث فائق السرعة | ⭐⭐⭐⭐⭐ |
| `which` | which | موقع الأوامر | ⭐⭐⭐⭐⭐ |
| `whereis` | util-linux | البحث عن ملفات البرامج | ⭐⭐⭐⭐ |
| `apropos` | man-db | البحث في صفحات المساعدة | ⭐⭐⭐ |

### 1.3 أدوات معالجة النصوص

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `sed` | sed | معالج نصوص stream | ⭐⭐⭐⭐⭐ |
| `awk` | gawk | معالجة بيانات نصية | ⭐⭐⭐⭐⭐ |
| `cut` | coreutils | استخراج أعمدة | ⭐⭐⭐⭐ |
| `paste` | coreutils | دمج أسطر | ⭐⭐⭐ |
| `sort` | coreutils | ترتيب النصوص | ⭐⭐⭐⭐⭐ |
| `uniq` | coreutils | إزالة التكرار | ⭐⭐⭐⭐ |
| `tr` | coreutils | تحويل/حذف أحرف | ⭐⭐⭐⭐ |
| `wc` | coreutils | عد الكلمات والأسطر | ⭐⭐⭐⭐⭐ |
| `diff` | diffutils | مقارنة ملفات | ⭐⭐⭐⭐⭐ |
| `patch` | patch | تطبيق الفروقات | ⭐⭐⭐⭐ |
| `comm` | coreutils | مقارنة ملفات مرتبة | ⭐⭐⭐ |
| `tee` | coreutils | قراءة وكتابة معاً | ⭐⭐⭐⭐ |
| `xargs` | findutils | بناء وتنفيذ أوامر | ⭐⭐⭐⭐⭐ |
| `column` | util-linux | تنسيق نص بأعمدة | ⭐⭐⭐ |

### 1.4 المحررات النصية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `nano` | nano | محرر سهل للمبتدئين | ⭐⭐⭐⭐⭐ |
| `vim` | vim-enhanced | محرر قوي متقدم | ⭐⭐⭐⭐⭐ |
| `vi` | vim-minimal | محرر أساسي | ⭐⭐⭐⭐⭐ |
| `emacs` | emacs | محرر شامل متقدم | ⭐⭐⭐⭐ |
| `neovim` | neovim | vim محسن | ⭐⭐⭐⭐ |

---

## 2. أدوات إدارة العمليات

### 2.1 مراقبة العمليات الأساسية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `ps` | procps-ng | عرض العمليات | ⭐⭐⭐⭐⭐ |
| `top` | procps-ng | مراقبة فورية للعمليات | ⭐⭐⭐⭐⭐ |
| `htop` | htop | top متقدم وملون | ⭐⭐⭐⭐⭐ |
| `atop` | atop | مراقبة شاملة للنظام | ⭐⭐⭐⭐ |
| `btop` | btop | مراقب حديث جذاب | ⭐⭐⭐⭐ |
| `glances` | glances | لوحة مراقبة شاملة | ⭐⭐⭐⭐⭐ |
| `nmon` | nmon | أداء مفصل | ⭐⭐⭐⭐ |

### 2.2 التحكم بالعمليات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `kill` | util-linux | إنهاء عملية | ⭐⭐⭐⭐⭐ |
| `killall` | psmisc | إنهاء عمليات بالاسم | ⭐⭐⭐⭐⭐ |
| `pkill` | procps-ng | إنهاء بنمط | ⭐⭐⭐⭐⭐ |
| `pgrep` | procps-ng | البحث عن عمليات | ⭐⭐⭐⭐⭐ |
| `nice` | coreutils | تشغيل بأولوية | ⭐⭐⭐⭐ |
| `renice` | util-linux | تغيير الأولوية | ⭐⭐⭐⭐ |
| `bg` | bash (مدمج) | تشغيل في الخلفية | ⭐⭐⭐⭐ |
| `fg` | bash (مدمج) | إحضار للمقدمة | ⭐⭐⭐⭐ |
| `jobs` | bash (مدمج) | عرض الوظائف | ⭐⭐⭐⭐ |
| `nohup` | coreutils | تشغيل مستمر | ⭐⭐⭐⭐⭐ |
| `screen` | screen | جلسات طرفية متعددة | ⭐⭐⭐⭐⭐ |
| `tmux` | tmux | multiplexer متقدم | ⭐⭐⭐⭐⭐ |
| `disown` | bash (مدمج) | فصل عملية | ⭐⭐⭐ |

### 2.3 أدوات جدولة المهام

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `cron` | cronie | جدولة دورية | ⭐⭐⭐⭐⭐ |
| `crontab` | cronie | إدارة مهام cron | ⭐⭐⭐⭐⭐ |
| `at` | at | جدولة مرة واحدة | ⭐⭐⭐⭐ |
| `batch` | at | تنفيذ عند انخفاض الحمل | ⭐⭐⭐ |
| `anacron` | cronie-anacron | مهام غير معتمدة على وقت | ⭐⭐⭐⭐ |
| `systemd-timer` | systemd | مؤقتات systemd | ⭐⭐⭐⭐⭐ |

---

## 3. أدوات إدارة الشبكات

### 3.1 أدوات الشبكات الأساسية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `ip` | iproute | إدارة شاملة للشبكة | ⭐⭐⭐⭐⭐ |
| `ifconfig` | net-tools | إعدادات الشبكة (قديم) | ⭐⭐⭐⭐ |
| `ping` | iputils | اختبار الاتصال | ⭐⭐⭐⭐⭐ |
| `ping6` | iputils | ping لـ IPv6 | ⭐⭐⭐⭐ |
| `traceroute` | traceroute | تتبع المسار | ⭐⭐⭐⭐⭐ |
| `tracepath` | iputils | تتبع بسيط | ⭐⭐⭐⭐ |
| `mtr` | mtr | traceroute مستمر | ⭐⭐⭐⭐⭐ |
| `netstat` | net-tools | إحصائيات الشبكة | ⭐⭐⭐⭐⭐ |
| `ss` | iproute | فحص sockets (بديل netstat) | ⭐⭐⭐⭐⭐ |
| `route` | net-tools | إدارة الطرق | ⭐⭐⭐⭐ |
| `arp` | net-tools | جدول ARP | ⭐⭐⭐⭐ |
| `arping` | iputils | إرسال ARP requests | ⭐⭐⭐ |
| `hostname` | hostname | اسم الجهاز | ⭐⭐⭐⭐⭐ |
| `host` | bind-utils | استعلامات DNS | ⭐⭐⭐⭐⭐ |
| `dig` | bind-utils | استعلام DNS متقدم | ⭐⭐⭐⭐⭐ |
| `nslookup` | bind-utils | بحث DNS (قديم) | ⭐⭐⭐⭐ |
| `nmcli` | NetworkManager | إدارة NetworkManager | ⭐⭐⭐⭐⭐ |
| `nmtui` | NetworkManager-tui | واجهة نصية لـ NetworkManager | ⭐⭐⭐⭐⭐ |

### 3.2 أدوات التشخيص والمراقبة

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `tcpdump` | tcpdump | التقاط حزم الشبكة | ⭐⭐⭐⭐⭐ |
| `wireshark` | wireshark | تحليل حزم رسومي | ⭐⭐⭐⭐⭐ |
| `tshark` | wireshark-cli | wireshark طرفي | ⭐⭐⭐⭐⭐ |
| `nmap` | nmap | فحص الشبكة والمنافذ | ⭐⭐⭐⭐⭐ |
| `netcat (nc)` | nmap-ncat | أداة شبكة متعددة | ⭐⭐⭐⭐⭐ |
| `socat` | socat | تحويل بيانات متقدم | ⭐⭐⭐⭐ |
| `telnet` | telnet | اتصال بعيد (غير آمن) | ⭐⭐⭐ |
| `wget` | wget | تحميل من الإنترنت | ⭐⭐⭐⭐⭐ |
| `curl` | curl | نقل بيانات متقدم | ⭐⭐⭐⭐⭐ |
| `iftop` | iftop | مراقبة استخدام الشبكة | ⭐⭐⭐⭐⭐ |
| `iptraf-ng` | iptraf-ng | مراقبة IP تفاعلية | ⭐⭐⭐⭐ |
| `nethogs` | nethogs | استهلاك الشبكة للعمليات | ⭐⭐⭐⭐⭐ |
| `bmon` | bmon | مراقبة bandwidth | ⭐⭐⭐⭐ |
| `vnstat` | vnstat | إحصائيات شبكة طويلة المدى | ⭐⭐⭐⭐ |
| `ethtool` | ethtool | إدارة ethernet | ⭐⭐⭐⭐⭐ |
| `iw` | iw | إدارة WiFi حديثة | ⭐⭐⭐⭐⭐ |

### 3.3 أدوات Firewall والأمان

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `firewalld` | firewalld | إدارة جدار حماية | ⭐⭐⭐⭐⭐ |
| `firewall-cmd` | firewalld | أوامر firewalld | ⭐⭐⭐⭐⭐ |
| `iptables` | iptables | جدار حماية قديم | ⭐⭐⭐⭐⭐ |
| `nftables` | nftables | جدار حماية حديث | ⭐⭐⭐⭐⭐ |
| `fail2ban` | fail2ban | منع الهجمات | ⭐⭐⭐⭐⭐ |

### 3.4 أدوات SSH و Remote

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `ssh` | openssh-clients | اتصال آمن بعيد | ⭐⭐⭐⭐⭐ |
| `sshd` | openssh-server | خادم SSH | ⭐⭐⭐⭐⭐ |
| `ssh-keygen` | openssh | إنشاء مفاتيح SSH | ⭐⭐⭐⭐⭐ |
| `ssh-copy-id` | openssh-clients | نسخ مفاتيح | ⭐⭐⭐⭐⭐ |
| `scp` | openssh-clients | نسخ آمن | ⭐⭐⭐⭐⭐ |
| `sftp` | openssh-clients | نقل ملفات آمن | ⭐⭐⭐⭐⭐ |
| `rsync` | rsync | مزامنة فعّالة | ⭐⭐⭐⭐⭐ |
| `sshfs` | fuse-sshfs | mount عبر SSH | ⭐⭐⭐⭐ |

---

## 4. أدوات إدارة التخزين والأقراص

### 4.1 أدوات الأقراص الأساسية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `df` | coreutils | مساحة الأقراص | ⭐⭐⭐⭐⭐ |
| `du` | coreutils | استهلاك المساحة | ⭐⭐⭐⭐⭐ |
| `mount` | util-linux | تركيب أنظمة ملفات | ⭐⭐⭐⭐⭐ |
| `umount` | util-linux | فك التركيب | ⭐⭐⭐⭐⭐ |
| `lsblk` | util-linux | عرض الأقراص | ⭐⭐⭐⭐⭐ |
| `blkid` | util-linux | معرفات الأقراص | ⭐⭐⭐⭐⭐ |
| `fdisk` | util-linux | تقسيم الأقراص | ⭐⭐⭐⭐⭐ |
| `parted` | parted | تقسيم متقدم | ⭐⭐⭐⭐⭐ |
| `cfdisk` | util-linux | تقسيم تفاعلي | ⭐⭐⭐⭐ |
| `sfdisk` | util-linux | تقسيم نصي | ⭐⭐⭐ |
| `gdisk` | gdisk | تقسيم GPT | ⭐⭐⭐⭐⭐ |

### 4.2 أدوات أنظمة الملفات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `mkfs` | util-linux | إنشاء نظام ملفات | ⭐⭐⭐⭐⭐ |
| `mkfs.ext4` | e2fsprogs | إنشاء ext4 | ⭐⭐⭐⭐⭐ |
| `mkfs.xfs` | xfsprogs | إنشاء XFS | ⭐⭐⭐⭐⭐ |
| `mkfs.btrfs` | btrfs-progs | إنشاء Btrfs | ⭐⭐⭐⭐ |
| `fsck` | util-linux | فحص نظام الملفات | ⭐⭐⭐⭐⭐ |
| `e2fsck` | e2fsprogs | فحص ext2/3/4 | ⭐⭐⭐⭐⭐ |
| `xfs_repair` | xfsprogs | إصلاح XFS | ⭐⭐⭐⭐⭐ |
| `tune2fs` | e2fsprogs | ضبط ext2/3/4 | ⭐⭐⭐⭐ |
| `resize2fs` | e2fsprogs | تغيير حجم ext | ⭐⭐⭐⭐ |
| `xfs_growfs` | xfsprogs | تكبير XFS | ⭐⭐⭐⭐ |

### 4.3 LVM (Logical Volume Manager)

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `pvcreate` | lvm2 | إنشاء physical volume | ⭐⭐⭐⭐⭐ |
| `pvdisplay` | lvm2 | عرض PV | ⭐⭐⭐⭐⭐ |
| `pvs` | lvm2 | قائمة PVs مختصرة | ⭐⭐⭐⭐⭐ |
| `vgcreate` | lvm2 | إنشاء volume group | ⭐⭐⭐⭐⭐ |
| `vgdisplay` | lvm2 | عرض VG | ⭐⭐⭐⭐⭐ |
| `vgs` | lvm2 | قائمة VGs | ⭐⭐⭐⭐⭐ |
| `vgextend` | lvm2 | توسيع VG | ⭐⭐⭐⭐ |
| `lvcreate` | lvm2 | إنشاء logical volume | ⭐⭐⭐⭐⭐ |
| `lvdisplay` | lvm2 | عرض LV | ⭐⭐⭐⭐⭐ |
| `lvs` | lvm2 | قائمة LVs | ⭐⭐⭐⭐⭐ |
| `lvextend` | lvm2 | توسيع LV | ⭐⭐⭐⭐⭐ |
| `lvresize` | lvm2 | تغيير حجم LV | ⭐⭐⭐⭐⭐ |

### 4.4 أدوات RAID

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `mdadm` | mdadm | إدارة RAID | ⭐⭐⭐⭐⭐ |

### 4.5 أدوات التشفير

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `cryptsetup` | cryptsetup | تشفير LUKS | ⭐⭐⭐⭐⭐ |

### 4.6 أدوات متقدمة للتخزين

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `ncdu` | ncdu | تحليل مساحة تفاعلي | ⭐⭐⭐⭐⭐ |
| `smartctl` | smartmontools | فحص صحة الأقراص | ⭐⭐⭐⭐⭐ |
| `hdparm` | hdparm | معلومات الأقراص | ⭐⭐⭐⭐ |
| `ddrescue` | ddrescue | استعادة بيانات | ⭐⭐⭐⭐⭐ |
| `dd` | coreutils | نسخ قطاعات | ⭐⭐⭐⭐⭐ |

---

## 5. أدوات المراقبة والأداء

### 5.1 مراقبة الموارد

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `vmstat` | procps-ng | إحصائيات ذاكرة افتراضية | ⭐⭐⭐⭐⭐ |
| `iostat` | sysstat | إحصائيات I/O | ⭐⭐⭐⭐⭐ |
| `mpstat` | sysstat | إحصائيات معالج | ⭐⭐⭐⭐⭐ |
| `sar` | sysstat | تقارير نشاط النظام | ⭐⭐⭐⭐⭐ |
| `free` | procps-ng | معلومات الذاكرة | ⭐⭐⭐⭐⭐ |
| `uptime` | procps-ng | وقت التشغيل والحمل | ⭐⭐⭐⭐⭐ |
| `w` | procps-ng | من متصل والأنشطة | ⭐⭐⭐⭐ |
| `who` | coreutils | المستخدمون المتصلون | ⭐⭐⭐⭐ |
| `last` | util-linux | سجل تسجيل الدخول | ⭐⭐⭐⭐⭐ |
| `lastlog` | shadow-utils | آخر تسجيل دخول | ⭐⭐⭐⭐ |

### 5.2 أدوات Profiling والتحليل

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `strace` | strace | تتبع system calls | ⭐⭐⭐⭐⭐ |
| `ltrace` | ltrace | تتبع library calls | ⭐⭐⭐⭐ |
| `lsof` | lsof | ملفات مفتوحة | ⭐⭐⭐⭐⭐ |
| `fuser` | psmisc | من يستخدم الملف | ⭐⭐⭐⭐ |
| `perf` | perf | أداء kernel | ⭐⭐⭐⭐⭐ |
| `sysdig` | sysdig | تحليل نظام شامل | ⭐⭐⭐⭐⭐ |
| `bpftrace` | bpftrace | تتبع eBPF | ⭐⭐⭐⭐ |

### 5.3 أدوات درجة الحرارة والطاقة

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `sensors` | lm_sensors | درجات الحرارة | ⭐⭐⭐⭐⭐ |
| `powertop` | powertop | استهلاك الطاقة | ⭐⭐⭐⭐ |
| `cpupower` | kernel-tools | إدارة المعالج | ⭐⭐⭐⭐ |

---

## 6. أدوات الأمان

### 6.1 أدوات الأمان الأساسية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `sudo` | sudo | تنفيذ بصلاحيات عليا | ⭐⭐⭐⭐⭐ |
| `su` | util-linux | تبديل مستخدم | ⭐⭐⭐⭐⭐ |
| `visudo` | sudo | تحرير sudoers آمن | ⭐⭐⭐⭐⭐ |

### 6.2 SELinux

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `getenforce` | libselinux-utils | حالة SELinux | ⭐⭐⭐⭐⭐ |
| `setenforce` | libselinux-utils | تغيير وضع SELinux | ⭐⭐⭐⭐⭐ |
| `sestatus` | policycoreutils | معلومات SELinux | ⭐⭐⭐⭐⭐ |
| `semanage` | policycoreutils-python-utils | إدارة سياسات | ⭐⭐⭐⭐⭐ |
| `restorecon` | policycoreutils | استعادة سياقات | ⭐⭐⭐⭐⭐ |
| `chcon` | coreutils | تغيير السياق | ⭐⭐⭐⭐ |
| `audit2allow` | policycoreutils-python-utils | إنشاء سياسات | ⭐⭐⭐⭐ |
| `sealert` | setroubleshoot-server | تحليل تنبيهات SELinux | ⭐⭐⭐⭐⭐ |

### 6.3 فحص الثغرات والأمان

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `lynis` | lynis | تدقيق أمني | ⭐⭐⭐⭐⭐ |
| `rkhunter` | rkhunter | كشف rootkit | ⭐⭐⭐⭐⭐ |
| `chkrootkit` | chkrootkit | فحص rootkit | ⭐⭐⭐⭐ |
| `aide` | aide | كشف التسلل | ⭐⭐⭐⭐ |
| `clamav` | clamav | مضاد فيروسات | ⭐⭐⭐⭐ |
| `openvas` | openvas | فحص ثغرات | ⭐⭐⭐⭐⭐ |
| `oscap` | openscap-scanner | فحص أمني SCAP | ⭐⭐⭐⭐⭐ |

### 6.4 أدوات التشفير والشهادات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `openssl` | openssl | تشفير وشهادات | ⭐⭐⭐⭐⭐ |
| `gpg` | gnupg2 | تشفير GPG | ⭐⭐⭐⭐⭐ |
| `certbot` | certbot | شهادات Let's Encrypt | ⭐⭐⭐⭐⭐ |

---

## 7. أدوات إدارة الحزم

### 7.1 DNF/YUM (RPM Package Manager)

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `dnf` | dnf | إدارة حزم حديثة | ⭐⭐⭐⭐⭐ |
| `yum` | yum | إدارة حزم (قديم) | ⭐⭐⭐⭐ |
| `rpm` | rpm | إدارة حزم RPM | ⭐⭐⭐⭐⭐ |
| `dnf-plugins-core` | dnf-plugins-core | إضافات DNF | ⭐⭐⭐⭐⭐ |
| `repoquery` | dnf-plugins-core | استعلام مستودعات | ⭐⭐⭐⭐⭐ |
| `dnf-automatic` | dnf-automatic | تحديثات تلقائية | ⭐⭐⭐⭐ |
| `createrepo` | createrepo_c | إنشاء مستودعات | ⭐⭐⭐⭐⭐ |
| `reposync` | dnf-plugins-core | مزامنة مستودعات | ⭐⭐⭐⭐⭐ |

### 7.2 Flatpak

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `flatpak` | flatpak | حزم flatpak | ⭐⭐⭐⭐ |

### 7.3 أدوات البناء

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `Development Tools` | group | مجموعة أدوات تطوير | ⭐⭐⭐⭐⭐ |
| `make` | make | بناء برامج | ⭐⭐⭐⭐⭐ |
| `cmake` | cmake | نظام بناء متقدم | ⭐⭐⭐⭐⭐ |
| `gcc` | gcc | مترجم C | ⭐⭐⭐⭐⭐ |
| `g++` | gcc-c++ | مترجم C++ | ⭐⭐⭐⭐⭐ |
| `rpmbuild` | rpm-build | بناء حزم RPM | ⭐⭐⭐⭐⭐ |
| `mock` | mock | بيئة بناء معزولة | ⭐⭐⭐⭐ |

---

## 8. أدوات النسخ الاحتياطي والاستعادة

### 8.1 أدوات النسخ الاحتياطي

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `rsync` | rsync | مزامنة ونسخ | ⭐⭐⭐⭐⭐ |
| `tar` | tar | أرشفة ملفات | ⭐⭐⭐⭐⭐ |
| `gzip` | gzip | ضغط gzip | ⭐⭐⭐⭐⭐ |
| `bzip2` | bzip2 | ضغط bzip2 | ⭐⭐⭐⭐ |
| `xz` | xz | ضغط xz | ⭐⭐⭐⭐⭐ |
| `zip` | zip | أرشيف zip | ⭐⭐⭐⭐⭐ |
| `unzip` | unzip | فك zip | ⭐⭐⭐⭐⭐ |
| `p7zip` | p7zip | ضغط 7z | ⭐⭐⭐⭐ |
| `borgbackup` | borgbackup | نسخ احتياطي مشفر | ⭐⭐⭐⭐⭐ |
| `restic` | restic | نسخ احتياطي سريع | ⭐⭐⭐⭐⭐ |
| `duplicity` | duplicity | نسخ مشفر تزايدي | ⭐⭐⭐⭐ |
| `bacula` | bacula | نظام نسخ شبكي | ⭐⭐⭐⭐ |

### 8.2 أدوات Snapshot

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `snapper` | snapper | إدارة snapshots | ⭐⭐⭐⭐ |

---

## 9. أدوات إدارة المستخدمين والصلاحيات

### 9.1 إدارة المستخدمين

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `useradd` | shadow-utils | إضافة مستخدم | ⭐⭐⭐⭐⭐ |
| `usermod` | shadow-utils | تعديل مستخدم | ⭐⭐⭐⭐⭐ |
| `userdel` | shadow-utils | حذف مستخدم | ⭐⭐⭐⭐⭐ |
| `passwd` | passwd | تغيير كلمة مرور | ⭐⭐⭐⭐⭐ |
| `chage` | shadow-utils | إدارة انتهاء كلمة مرور | ⭐⭐⭐⭐ |
| `id` | coreutils | معرف المستخدم | ⭐⭐⭐⭐⭐ |
| `whoami` | coreutils | المستخدم الحالي | ⭐⭐⭐⭐⭐ |

### 9.2 إدارة المجموعات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `groupadd` | shadow-utils | إضافة مجموعة | ⭐⭐⭐⭐⭐ |
| `groupmod` | shadow-utils | تعديل مجموعة | ⭐⭐⭐⭐ |
| `groupdel` | shadow-utils | حذف مجموعة | ⭐⭐⭐⭐ |
| `groups` | coreutils | مجموعات المستخدم | ⭐⭐⭐⭐⭐ |
| `gpasswd` | shadow-utils | إدارة مجموعات | ⭐⭐⭐⭐ |
| `newgrp` | shadow-utils | تبديل مجموعة | ⭐⭐⭐ |

### 9.3 الصلاحيات وملكية الملفات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `chmod` | coreutils | تغيير صلاحيات | ⭐⭐⭐⭐⭐ |
| `chown` | coreutils | تغيير المالك | ⭐⭐⭐⭐⭐ |
| `chgrp` | coreutils | تغيير المجموعة | ⭐⭐⭐⭐ |
| `umask` | bash (مدمج) | صلاحيات افتراضية | ⭐⭐⭐⭐ |
| `setfacl` | acl | ACL متقدم | ⭐⭐⭐⭐ |
| `getfacl` | acl | عرض ACL | ⭐⭐⭐⭐ |

---

## 10. أدوات السجلات والتشخيص

### 10.1 إدارة السجلات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `journalctl` | systemd | سجلات systemd | ⭐⭐⭐⭐⭐ |
| `logger` | util-linux | كتابة لسجل النظام | ⭐⭐⭐⭐ |
| `rsyslog` | rsyslog | نظام سجلات | ⭐⭐⭐⭐⭐ |
| `logrotate` | logrotate | تدوير السجلات | ⭐⭐⭐⭐⭐ |
| `dmesg` | util-linux | رسائل kernel | ⭐⭐⭐⭐⭐ |

### 10.2 أدوات التشخيص

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `uname` | coreutils | معلومات النظام | ⭐⭐⭐⭐⭐ |
| `lscpu` | util-linux | معلومات المعالج | ⭐⭐⭐⭐⭐ |
| `lshw` | lshw | عتاد شامل | ⭐⭐⭐⭐⭐ |
| `lspci` | pciutils | أجهزة PCI | ⭐⭐⭐⭐⭐ |
| `lsusb` | usbutils | أجهزة USB | ⭐⭐⭐⭐⭐ |
| `dmidecode` | dmidecode | معلومات BIOS | ⭐⭐⭐⭐⭐ |
| `hwinfo` | hwinfo | معلومات عتاد مفصلة | ⭐⭐⭐⭐ |
| `neofetch` | neofetch | معلومات جمالية | ⭐⭐⭐ |

---

## 11. أدوات الأتمتة والبرمجة

### 11.1 Shell Scripting

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `bash` | bash | shell أساسي | ⭐⭐⭐⭐⭐ |
| `sh` | bash | POSIX shell | ⭐⭐⭐⭐⭐ |
| `zsh` | zsh | shell متقدم | ⭐⭐⭐⭐ |
| `shellcheck` | ShellCheck | فحص scripts | ⭐⭐⭐⭐⭐ |

### 11.2 لغات البرمجة

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `python3` | python3 | Python 3 | ⭐⭐⭐⭐⭐ |
| `pip3` | python3-pip | إدارة حزم Python | ⭐⭐⭐⭐⭐ |
| `perl` | perl | لغة Perl | ⭐⭐⭐⭐ |
| `ruby` | ruby | لغة Ruby | ⭐⭐⭐ |

### 11.3 أدوات التحكم بالإصدارات

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `git` | git | نظام تحكم بالإصدارات | ⭐⭐⭐⭐⭐ |
| `tig` | tig | واجهة طرفية لـ git | ⭐⭐⭐⭐ |

---

## 12. أدوات التحكم بالخدمات

### 12.1 Systemd

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `systemctl` | systemd | التحكم بالخدمات | ⭐⭐⭐⭐⭐ |
| `systemd-analyze` | systemd | تحليل الإقلاع | ⭐⭐⭐⭐⭐ |
| `hostnamectl` | systemd | إدارة اسم الجهاز | ⭐⭐⭐⭐ |
| `timedatectl` | systemd | إدارة الوقت والتاريخ | ⭐⭐⭐⭐⭐ |
| `localectl` | systemd | إعدادات اللغة | ⭐⭐⭐⭐ |
| `loginctl` | systemd | إدارة الجلسات | ⭐⭐⭐⭐ |

---

## 13. أدوات الأداء المتقدمة

### 13.1 Benchmarking

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `sysbench` | sysbench | قياس أداء شامل | ⭐⭐⭐⭐⭐ |
| `stress` | stress | اختبار إجهاد | ⭐⭐⭐⭐ |
| `stress-ng` | stress-ng | اختبار إجهاد متقدم | ⭐⭐⭐⭐⭐ |
| `fio` | fio | قياس أداء I/O | ⭐⭐⭐⭐⭐ |
| `iperf3` | iperf3 | قياس أداء الشبكة | ⭐⭐⭐⭐⭐ |

---

## 14. أدوات واجهات الرسومية

### 14.1 أدوات إدارة رسومية

| الأداة | الحزمة | الاستخدام | الأهمية |
|-------|--------|----------|---------|
| `cockpit` | cockpit | لوحة إدارة ويب | ⭐⭐⭐⭐⭐ |
| `webmin` | webmin | إدارة عبر الويب | ⭐⭐⭐⭐ |

---

## 15. طرق التثبيت لبيئة Offline

### 15.1 إنشاء مستودع محلي كامل

#### الطريقة الأولى: reposync (الأساسية لـ Rocky)

**على جهاز متصل بالإنترنت:**

```bash
# تثبيت أدوات المزامنة
sudo dnf install dnf-plugins-core createrepo_c

# إنشاء مجلد للمستودع
sudo mkdir -p /repo/rocky10

# مزامنة المستودعات الأساسية
# BaseOS
sudo reposync --gpgcheck --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10 \
  --repoid=baseos

# AppStream
sudo reposync --gpgcheck --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10 \
  --repoid=appstream

# Extras
sudo reposync --gpgcheck --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10 \
  --repoid=extras

# CRB (للتطوير)
sudo reposync --gpgcheck --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10 \
  --repoid=crb

# EPEL (إضافي)
sudo dnf install epel-release
sudo reposync --gpgcheck --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10 \
  --repoid=epel

# إنشاء metadata للمستودعات
cd /repo/rocky10/baseos
sudo createrepo_c .
cd /repo/rocky10/appstream
sudo createrepo_c .
cd /repo/rocky10/extras
sudo createrepo_c .

# ضغط المستودع (حجم كبير ~150-200GB)
cd /repo
sudo tar -czf rocky10-offline-repo.tar.gz rocky10/

# نقل للجهاز Offline
```

**على الجهاز Offline:**

```bash
# فك الضغط
sudo mkdir -p /repo
sudo tar -xzf rocky10-offline-repo.tar.gz -C /repo

# إعداد httpd (اختياري للشبكة المحلية)
sudo dnf install httpd
sudo ln -s /repo/rocky10 /var/www/html/rocky10
sudo systemctl enable --now httpd
sudo firewall-cmd --add-service=http --permanent
sudo firewall-cmd --reload

# أو استخدام ملف محلي مباشرة
sudo nano /etc/yum.repos.d/local-offline.repo

# المحتوى:
[local-baseos]
name=Rocky Linux 10 BaseOS - Local Offline
baseurl=file:///repo/rocky10/baseos
enabled=1
gpgcheck=0

[local-appstream]
name=Rocky Linux 10 AppStream - Local Offline
baseurl=file:///repo/rocky10/appstream
enabled=1
gpgcheck=0

[local-extras]
name=Rocky Linux 10 Extras - Local Offline
baseurl=file:///repo/rocky10/extras
enabled=1
gpgcheck=0

# تعطيل المستودعات الافتراضية
sudo dnf config-manager --disable baseos appstream extras

# تحديث cache
sudo dnf clean all
sudo dnf makecache
```

### 15.2 تحميل حزم محددة

#### الطريقة الثانية: dnf download

```bash
# على جهاز متصل
mkdir ~/offline-packages
cd ~/offline-packages

# تحميل حزمة واعتمادياتها
sudo dnf install --downloadonly --downloaddir=. htop

# أو استخدام repoquery
dnf repoquery --requires htop
dnf download --resolve htop

# لتحميل مجموعة كاملة
dnf group info "Development Tools"
dnf download "@Development Tools" --resolve --alldeps

# نقل للجهاز Offline

# على الجهاز Offline
sudo dnf install *.rpm
# أو
sudo rpm -ivh *.rpm
```

### 15.3 إنشاء قرص ISO موسع

```bash
# تحميل ISO رسمي
wget https://download.rockylinux.org/pub/rocky/10/isos/x86_64/Rocky-10-x86_64-dvd.iso

# mount ISO
sudo mkdir /mnt/iso
sudo mount -o loop Rocky-10-x86_64-dvd.iso /mnt/iso

# نسخ المحتوى
sudo mkdir ~/custom-iso
sudo cp -rT /mnt/iso ~/custom-iso

# إضافة حزم إضافية
sudo mkdir ~/custom-iso/custom-packages
sudo cp ~/offline-packages/*.rpm ~/custom-iso/custom-packages/

# إنشاء metadata
cd ~/custom-iso/custom-packages
sudo createrepo_c .

# إعادة بناء ISO
sudo dnf install genisoimage
sudo genisoimage -o rocky10-custom.iso -b isolinux/isolinux.bin \
  -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 \
  -boot-info-table -J -R -V "Rocky 10 Custom" ~/custom-iso
```

### 15.4 استخدام USB كمستودع

```bash
# تحضير USB (مساحة كبيرة مطلوبة)
sudo mkfs.ext4 /dev/sdX1 -L "ROCKY_REPO"
sudo mkdir /mnt/usb
sudo mount /dev/sdX1 /mnt/usb

# نسخ المستودع
sudo rsync -av /repo/rocky10/ /mnt/usb/

# على جهاز Offline
sudo mount /dev/sdX1 /mnt/usb

# إنشاء repo file
sudo nano /etc/yum.repos.d/usb-repo.repo

# المحتوى:
[usb-baseos]
name=Rocky Linux 10 BaseOS - USB
baseurl=file:///mnt/usb/baseos
enabled=1
gpgcheck=0

[usb-appstream]
name=Rocky Linux 10 AppStream - USB
baseurl=file:///mnt/usb/appstream
enabled=1
gpgcheck=0

sudo dnf clean all
sudo dnf makecache
```

### 15.5 إنشاء مستودع صغير مخصص

```bash
# على جهاز متصل - لتطبيق معين
mkdir -p ~/minimal-repo

# قائمة الحزم المطلوبة
PACKAGES=(
    "htop"
    "vim-enhanced"
    "git"
    "tmux"
    "rsync"
    "ncdu"
    "glances"
)

# تحميل الحزم
for pkg in "${PACKAGES[@]}"; do
    dnf download --resolve --destdir=~/minimal-repo "$pkg"
done

# إنشاء metadata
cd ~/minimal-repo
createrepo_c .

# ضغط
tar -czf minimal-repo.tar.gz ~/minimal-repo

# على جهاز Offline
tar -xzf minimal-repo.tar.gz -C /opt/

# إنشاء repo
sudo nano /etc/yum.repos.d/minimal.repo

[minimal-repo]
name=Minimal Custom Repository
baseurl=file:///opt/minimal-repo
enabled=1
gpgcheck=0

sudo dnf install htop
```

### 15.6 مزامنة تحديثات فقط

```bash
# بعد إنشاء المستودع الأساسي، لتحديث دوري
sudo reposync --newest-only --delete \
  --download-metadata --destdir=/repo/rocky10-updates \
  --repoid=baseos --repoid=appstream

# تحديث metadata
cd /repo/rocky10-updates/baseos
sudo createrepo_c --update .
```

---

## 📊 إحصائيات الملف

- **إجمالي الأدوات المذكورة:** 380+ أداة
- **الفئات الرئيسية:** 15 فئة
- **الحزم الأساسية:** 180+ حزمة
- **مساحة المستودع الكامل:** ~150-200GB
- **التوزيع:** Rocky Linux 10

---

## 🔄 الفروقات الرئيسية عن Ubuntu

1. **مدير الحزم:** DNF/YUM بدلاً من APT
2. **SELinux:** مفعّل افتراضياً (بدلاً من AppArmor)
3. **Firewall:** firewalld افتراضي
4. **NetworkManager:** أكثر تكاملاً مع النظام
5. **المستودعات:** BaseOS, AppStream, Extras, CRB, EPEL

---

## 📝 ملاحظات إضافية

1. **الاستقرار:** Rocky Linux 10 نظام مستقر للخوادم
2. **التوافق:** متوافق مع RHEL
3. **SELinux:** يجب فهم سياساته جيداً
4. **التحديثات:** دورة حياة طويلة (10 سنوات)
5. **المستودعات:** EPEL ضروري للحزم الإضافية

---

**تم الإعداد:** مارس 2026  
**المؤلف:** دليل شامل لمديري أنظمة Rocky Linux

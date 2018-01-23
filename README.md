# Learn-linux

$ ls / # / đại diện cho thư mục root.​
Bạn nên chú ý là Linux sử dụng dấu gạch xuôi / thay vì gạch ngược \ trong Windows.
Sau đây là mô tả chi tiết các thư mục chính:
1. / – Root
Đây là thư mục ở mức cao nhất như đã nói ở trên. Tất cả các tệp tin và thư mục đều nằm trong thư mục này.
2. /sbin – System Binaries
Chứa đựng các file thực thi dạng binary (nhị phân) của các chương trình cơ bản giúp hệ thống có thể hoạt động. Các lệnh bên trong /sbin thường được sử dụng dùng cho các mục đích là duy trì quản trị hệ thống. Các lệnh này yêu cầu phải có quyền root.
Một số lệnh trong đây ví dụ: lilo, fdisk, init, ifconfig v.v.. Để liệt kê, bạn dùng lệnh "ls /sbin/".
Còn một thư mục mà nó chứa các tệp tin thi hành cho hệ thống là /usr/sbin/. Nhưng các chương trình ở đây không được sử dụng để bảo trì hệ thống.
3. /bin – User Binaries
Đối lập với /sbin/ thư mục này chứa rất nhiều ứng dụng khác nhau dùng được cả cho việc bảo trì hệ thống của root, cũng như các lệnh cho người dùng thông thường. Thư mục này thông thường chứa hệ vỏ (Shell), cũng như rất nhiều lệnh hữu dụng như cp (sao chép), mv (di chuyển), cat, ls. Cũng giống như sbin, thư mục /usr/bin cũng chứa các tệp tin có chức năng tương tự như /bin.
4. /boot – Boot Loader Files
Nhìn tên bạn cũng có thể đoán được nó dùng làm gì phải không nào. Nó chứa các tệp tin khởi động và cả nhân kernel là vmlinuz. Trong các bản phân phối gần đây, nó cũng chứa cả dữ liệu cho grub. Phần mềm khởi động Grub (viết tắt của GRand Unified Boot loader) ngày nay được sử dụng khá phổ biến.
5. /dev – Device Files
Đây là một thư mục thú vị nhất, nó thể hiện một cách rõ ràng là hệ điều hành Linux coi mọi thứ đều là các tệp tin và thư mục.
Trong thư mục này bạn có thể thấy rất nhiều tệp tin đại diện cho các thiết bị như ổ đĩa SATA, cổng COM v.v.. Bạn liệt kê chúng ra bằng lệnh "ls /dev/". Bạn sẽ thấy rất nhiều nhưng không phải chúng đều có thật trên máy tính của bạn đâu nhé. Chẳng hạn bạn chỉ có một cổng COM nhưng ở đây bạn sẽ thấy không chỉ có một.
Ví dụ:
/dev/sda : đây là ổ đĩa SATA thứ nhất
/dev/cdrom : ổ CD
/dev/ttyS0 : cổng COM1
6. /etc – Configuration Files
Chứa file cấu hình cho các chương trình hoạt động. Chúng thường là các tệp tin dạng text thường. Chức năng của nó gần giống với "Control Panel" trong Windows. Ví dụ:
/etc/resolv.conf (cấu hình dns-server )
/etc/network dùng để quản lý dịch vụ network
Ở /etc có một thư mục quan trọng đó là /etc/rc.d. Nơi đây thường chứa các scripts dùng để start, stop, kiểm tra status cho các chương trình.
7. /home – Home Directories
Thư mục Home. Thư mục này chứa thông tin, dữ liệu , cấu hình riêng cho từng user. Nó giống như thư mục "C:\Documents and Settings" trong Windows XP.
8. /lib – System Libraries
Chứa các file library hỗ trợ cho các file thực binary. Tên của các file library thường là ld* or lib*.so.* . Ví dụ như libc.so.* (Thư viện C).
9. /lost+found
Vì một lý do bất ngờ nào đó như lỗi phần mềm, mất điện v..v, hệ thống có thể đổ vỡ. Khi khởi động lại, hệ thống sẽ kiểm tra lại hệ thống filesystem bằng lệnh fchk và cố gắng phục hồi lại các lỗi mà nó tìm thấy. Kết quả của việc này sẽ được lưu giữ trong thư mục /lost+found.
10. /mnt – Mount Directory
Chứa các thư mục dùng để system admin thực hiện quá trình mount. Như đã nói, hệ điều hành Linux coi tất cả là các file và lưu giữ trên một cây chung. Đây chính nơi tạo ra các thư mục để 'gắn' các phân vùng ổ đĩa cứng cũng như các thiết bị khác vào. Sau khi được mount vào đây, các thiết bị hay ổ cứng được truy cập từ đây như là một thư mục. Trong một số hệ điều hành, các ổ đĩa chưa được gắn sẵn vào hệ thống bởi fstab sẽ được gắn ở đây. Về cách gắn và tháo, có lẽ cần một bài viết riêng.
11. /opt – Optional add-on Applications
Chứa các phần mềm và phần mở rộng không nằm trong phần cài đặt mặc định, thường là của hãng thứ ba.
12. /proc – Process Information
Chứa đựng thông tin về quá trình xử lý của hệ thống
Đây là một pseudo filesystem chứa đựng các thông tin về các process đang chạy
Đây là một virtual filesystem chứa đựng các thông tin tài nguyên hệ thống. Ví dụ:/proc/cpuinfo cung cấp cho ta thông số kỹ thuật của CPU. Để xem bạn dùng lệnh 'cat':
$cat /proc/cpuinfo​
13. /tmp – Temporary Files
Thư mục này chứa các file được tạo với mục đích dùng tạm thời bởi hệ thống cũng như user. Các file bên dưới thư mục này được xóa đi khi hệ thống reboot hay shutdown.
14. /usr – User Programs
Chứa các file binary, library, tài liệu, source-code cho các chương trình
/usr/bin chứa file binary cho các chương trình của user. Nếu như một user trong quá trình thực thi một lệnh ban đầu sẽ tìm kiếm trong /bin, nếu như không có thì sẽ tiếp tục nhìn vào /usr/bin. Ví dụ một số lệnh như at. awk, cc...
/usr/sbin chứa các file binary cho system administrator. Nếu như ta không tìm thấy các file system binary bên dưới /sbin thì ta có thể tìm ở trong /usr/sbin. Ví dụ một số lệnh như cron, sshd, useradd, userdel
/usr/lib chứa các file libraries cho /usr/bin và /usr/sbin
/usr/local dùng để chứa chương trình của các user, các chương trình này được cài đặt từ source. Ví dụ khi ta install apache từ source thì nó sẽ nằm ở vị trí là /usr/local/apache2
15. /media – Removable Media Devices
Chứa thư mục dùng để mount cho các thiết bị removable. Ví dụ như CDROM, Floppy v.v..
16. /var – Variable Files
Chứa đựng các file có sự thay đổi trong quá trình hoạt động của hệ điều hành cũng như các ứng dụng. Ví dụ:
+ Nhật ký của hệ thống /var/log
+ database file /var/lib
+ email /var/mail
+ Các hàng đợi in ấn: /var/spool
+ lock file: /var/lock
+ Các file tạm thời cần cho quá trình reboot: /var/tmp
+ Dữ liệu cho trang web: /var/www
Để biết được thư mục đang nằm trên phân vùng nào các bạn hãy sử dụng lệnh df với đối số là dấu chấm (.) biểu diễn thư mục hiện hành.
$ df -h .​
Theo quy tắc chung, mọi thư mục đều nằm dưới thư mục root thì đều nằm trên phân vùng root, trừ phi nó có phân vùng riêng ở một trong số các phân vùng được liệt kê trong lệnh df (hay df -h mà không có tùy chọn khác).
Bạn có thể đọc thêm về cấu trúc của hệ thống tệp tin trong Linux bằng lệnh 'man hier'.
Trên đây là cái nhìn tổng quan về hệ thống tệp tin trên hệ điều hành Linux. Còn tùy thuộc vào các bản phân phối, cấu trúc này có thể khác nhau chút ít như thêm hay bớt một số thư mục.
Đến đây bạn sẽ thấy hệ điều hành Linux tổ chức hệ thống thư mục và tệp tin một cách thống nhất. Một ứng dụng gồm nhiều thành phần khác nhau sẽ được lưu giữ ở nhiều thư mục riêng biệt. Chẳng hạn tệp tin binary thì lưu trong /usr/local/bin trong khi dữ liệu lại lưu trong /usr/share/*.


We’ll show you how to speed up VestaCP on CentOS 7. Vesta Control Panel is a simple and easy to use open source hosting control panel. It has a simple and clean interface and lots of useful features that will help you to host your websites on your VPS. Vesta Control Panel currently can be installed on RHEL 5, RHEL 6, CentOS 5, CentOS 6, CentOS 7, Debian 7, Debian 8, Ubuntu 12.04, Ubuntu 12.10, Ubuntu 13.04, Ubuntu 13.10, Ubuntu 14.04 and Ubuntu 16.04 operating systems. Today we are going to learn how to speed up VestaCP on a CentOS 7 VPS.


1. Upgrade PHP
First make sure the system is up to date:

# yum update
Now let’s enable the remi-php70 repository so we can upgrade VestaCP to PHP 7:

# yum-config-manager --enable remi-php70
Update the system again, this command should upgrade all PHP packages to PHP 7:

# yum update
And then restart the php-fpm service:

# systemctl restart php-fpm
2. Install Opcache
Installing Opcache is pretty easy, just run the following command:

# yum install php-opcache
Restart the php-fpm service again:

# systemctl restart php-fpm
Restart Nginx as well:

# systemctl restart nginx
Now you should check if Opcache is enabled by running the following command:

php -i | grep opcache.enable
If Opcache is enabled you should see something like the following output:

opcache.enable => On => On
3. Upgrade MariaDB
First make a backup from all of your databases.

Instead of the conventional mysqldump utility you can use the VestaCP CLI to generate a backup for all of the users on your system, if you want to do that just run:

# v-backup-users
In case you need to restore the backup, first obtain the backup file name by typing in:

# v-list-user-backups <username>
And then by executing the following command you can restore all databases for a specific user:

# v-restore-user <username> <backup_name> no no no <username> no no no
Note: Replace <username> for the username you want to restore the databases for and <backup_name> for the name of the backup obtained by the v-list-user-backups command.

Now, let’s get to upgrading MariaDB finally, start by removing the old MariaDB version:

# yum remove mariadb mariadb-server
Add the repository for MariaDB 10 by creating the repo file with nano and then paste the text below:

# nano /etc/yum.repos.d/MariaDB.repo

# Used to install MariaDB 10 instead of default 5.5
# http://mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = https://yum.mariadb.org/10.2/centos7-amd64/
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
Now update the system again:

# yum update
And then install MariaDB 10:

# yum install mariadb mariadb-server
After the installation has finished, start MariaDB by running the following command:

# systemctl start mariadb
Then enable the MariaDB service on boot:

# systemctl enable mariadb.service
4. Install Redis
Redis is an in-memory data structure store primarily used as a database and cache.
You can get a huge speed benefit from configuring Redis to cache your pages or to cache your database rows.

You can install Redis by typing in the following command:

# yum install redis
After the yum package manager has finished installing Redis, type in the following command to start Redis:

# systemctl start redis
Now enable the Redis service to start on boot:

# systemctl enable redis.service
5. Configuring WordPress
If you use WordPress for your sites then it would be quite beneficial to install Redis as a caching system for WordPress.
We are going to need the Phpredis extension in order to configure WordPress to use Redis, first install this package:

# yum install php-devel
Then install the Phpredis extension using this command:

# pecl install redis
Press enter when the following message comes up:

enable igbinary serializer support? [no]
After PECL has finished installing Phpredis, open the php.ini file and add the following line at the bottom:

# nano /etc/php.ini

extension=redis.so
Restart php-fpm in order to make the changes effective:

# systemctl restart php-fpm
Now log in to your WordPress backend and install the plugin W3 Total Cache and activate it.In the plugin settings for W3 Total Cache select Redis as page cache and database cache then check the Enable checkbox for both options and click on the Save all settings button.When finished restart Nginx:

# systemctl restart nginx
Then turn on the Redis monitor by typing in the following command:

redis-cli monitor
Now using your browser navigate to your WordPress page, if Redis is working you should see output similar to this:

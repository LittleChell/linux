# linux
###### Linux 安装包过程中出现的错误及解决方法。
* * *

#####	1.	 dpkg:处理软件包 xxx (--configure)时出错

	
	i.	将info文件夹更名

		sudo mv /var/lib/dpkg/info /var/lib/dpkg/info_old
  
	ii.	再新建一个新的info文件夹
	
		sudo mkdir /var/lib/dpkg/info  

	iii.更新

		sudo apt-get update  
		sudo apt-get -f install  

	iv.	执行完上一步操作后会在新的info文件夹下生成一些文件，现将这些文件全部移到info_old文件夹下
	
		sudo mv /var/lib/dpkg/info/* /var/lib/dpkg/info_old   

	v.	把自己新建的info文件夹删掉
	
		sudo rm -rf /var/lib/dpkg/info  

	vi.	把以前的info文件夹重新改回名字
	
		sudo mv /var/lib/dpkg/info_old /var/lib/dpkg/info   



	
	
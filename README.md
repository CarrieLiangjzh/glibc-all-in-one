https://blog.csdn.net/PHILICS7/article/details/134512178

# glibc-all-in-one

1. clone the repository to local, the repository is : https://github.com/matrix1001/glibc-all-in-one

  sudo git clone https://github.com/matrix1001/glibc-all-in-one

2. enter into the folder, run update_list
   tips:
   1. error message: /usr/bin/python: bad interpreter: No such file or directory,
      If Python is not installed on your laptop, please install it first.
      if you already have Python installed, please check the version and the name in /usr/bin
      
      jingzhe@SG-NL-LINUX-006:/usr/bin$  ls -alh /usr/bin/pyt*
      lrwxrwxrwx 1 root root   10 aug 18  2022 /usr/bin/python3 -> python3.10
      -rwxr-xr-x 1 root root 5,7M mrt 22 17:50 /usr/bin/python3.10
      lrwxrwxrwx 1 root root   34 mrt 22 17:50 /usr/bin/python3.10-config -> x86_64-linux-gnu-python3.10-config
      lrwxrwxrwx 1 root root   17 aug 18  2022 /usr/bin/python3-config -> python3.10-config
      -rwxr-xr-x 1 root root  960 jan 25  2023 /usr/bin/python3-futurize
      -rwxr-xr-x 1 root root  964 jan 25  2023 /usr/bin/python3-pasteurize
      -rwxr-xr-x 1 root root 2,5K feb 27  2021 /usr/bin/python-argcomplete-check-easy-install-script3
      -rwxr-xr-x 1 root root  314 feb 27  2021 /usr/bin/python-argcomplete-tcsh3

      In my case, python3 is displayed instead of phython.
      
      Then let us edit the file update_list.
      First, add the write permit to this file, it is read only by default.
      
      `sudo chmod a+w update_list`

      Second, change the first line(just in my case)

      #!/usr/bin/python     to   #!/usr/bin/python3
      save, and run ./update_list, hope the problem is solved on your laotop.
   2. error message:  ModuleNotFoundError: No module named 'requests'
  
      sudo apt-get --reinstall install python3-requests

   3. download glibc package that you need.
      Check the "download" file, to find ou the download website(the url:http://archive.ubuntu.com/ubuntu/pool/main/g/glibc/
      and you can check all the glib package there, the name can be different from the update_list, please check and change the download file, to make sure the download can be successfully done.
   4. sudo ./build  "glibc version" "process type"
         glibc version": the version you just want to build/you downloaded
         process rype: your laptop process type
         you can run sudo ./build,then the supportted info will be printed，like：
         
         supported version: 2.19, 2.23-2.29
         supported arch: i686, amd64
          
     
         

  


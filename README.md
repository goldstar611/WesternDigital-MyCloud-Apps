# wd_mycloud_apps
How to do custom Western Digital MyCloud Apps

## create or resign apkg.sign:
  ```
  openssl bf-cbc -e -out apkg.sign -k Lidho.mdk3K3h -md md5
  << enterpackage name>>[CTRL+D][CTRL+D]
  ```
## check signature
  `openssl bf-cbc -d -in apkg.sign -k Lidho.mdk3K3h -md md5`
  
## extract tar.gz from .bin file
  #### OS 3 package
  `dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=200 iflag=skip_bytes,count_bytes`
  #### OS 5 package
  `dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=204 iflag=skip_bytes,count_bytes`

## Create a .bin
  `cd my_app/`
  `MyCloudOS5_mksapkg -E -s -m WDMyCloud`

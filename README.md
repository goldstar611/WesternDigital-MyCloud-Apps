# wd_mycloud_apps
How to do custom Western Digital MyCloud Apps

Tips:
* MyCloud OS3 uses `md5` for apkg.sign and `skip=200` to extract the .tar.gz from the .bin
* MyCloud OS5 uses `sha256` for apkg.sign and `skip=204` to extract the .tar.gz from the .bin

## create or resign apkg.sign:
  ```
  openssl bf-cbc -e -out apkg.sign -k Lidho.mdk3K3h -md sha256
  << enterpackage name>>[CTRL+D][CTRL+D]
  ```
## check signature
  #### OS 3 package
  `openssl bf-cbc -d -in apkg.sign -k Lidho.mdk3K3h -md md5`
  #### OS 5 package
  `openssl bf-cbc -d -in apkg.sign -k Lidho.mdk3K3h -md sha256`
  
## extract tar.gz from .bin file
  #### OS 3 package
  `dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=200 iflag=skip_bytes,count_bytes`
  #### OS 5 package
  `dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=204 iflag=skip_bytes,count_bytes`

## Create a .bin
  `cd my_app/`
  `MyCloudOS5_mksapkg -E -s -m WDMyCloud`

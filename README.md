# wd_mycloud_apps
How to do custom Western Digital MyCloud Apps

## update
  openssl bf-cbc -e -out apkg.sign -k Lidho.mdk3K3h -md md5
    <<enter package name>>[CTRL+D][CTRL+D]
## check
  openssl bf-cbc -d -in apkg.sign -k Lidho.mdk3K3h -md md5
## extract
  dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=200 iflag=skip_bytes,count_bytes

# wd_mycloud_apps
How to do custom Western Digital MyCloud Apps

## create or resign apkg.sign:
  `openssl bf-cbc -e -out apkg.sign -k Lidho.mdk3K3h -md md5`
    << enterpackage name>>[CTRL+D][CTRL+D]
## check
  `openssl bf-cbc -d -in apkg.sign -k Lidho.mdk3K3h -md md5`
  
## extract tar.gz from .bin file
  `dd if=transmission_MyCloud_2.94-16.bin of=temp.tar.gz skip=200 iflag=skip_bytes,count_bytes`

## Create a .bin
  `mkpkg32_forced_md5 -E -s -m WDMyCloud <.tar.gz file>`


source: https://fox-exe.ru/WDMyCloud/WDMyCloud-Gen2/Apps/
============ EN ============
1. Go to web interface
2.a In "URL" field (In your browser) type:
javascript:APP_INSTALL_FUNCTION=1; APPS_EULA=1; check_app_eula();
2.b Alternative way: Press [ctrl] + [shift] + [i], open "Console" tab, put this and hit [enter]:
APP_INSTALL_FUNCTION=1; APPS_EULA=1; check_app_eula();
3. Go to Apps tab and install "WD_Crack" app.
4. Refresh page and install any other apps.

***
Thx franfj from WD Community for this method.
https://community.wd.com/t/wd-mycloud-gen2-enable-apps-install-tab-apps/177885/117


***
# Alternative:
# Press [ctrl] + [shift] + [i], open "Console" tab, put this:
$("#AppsDiag_Manually_Install").remove();
var input = '<input type="file" name="f_apps_file" class="file_input_hidden" id="f_apps_file" onchange="apps_manually_install();">Install an app manually</div>';
$("#manually_install_td").append(input);

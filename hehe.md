ftp 10.200.58.192

nohup java -Xms10g -Xmx10g -Xmn1g -Xss256k -XX:PermSize=256m -XX:MaxPermSize=256m -jar -Dmode=product -DdisableCommonConf admin_content_radar-0.0.1.jar &

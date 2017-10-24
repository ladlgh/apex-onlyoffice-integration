# ONLYOFFICE integration in Oracle APEX

![](https://github.com/Dani3lSun/apex-onlyoffice-integration/blob/master/preview_docx.png)
![](https://github.com/Dani3lSun/apex-onlyoffice-integration/blob/master/preview_xlsx.png)

[DEMO APPLICATION](https://orclapex.io/ords/f?p=170)


## Installation DB / APEX

1. table
```
@src/01_files_table.sql
```

2. sequence
```
@src/02_files_sequence.sql
```

3. trigger
```
@src/03_files_trigger.sql
```

4. package
```
@src/onlyoffice_pkg.pks
@src/onlyoffice_pkg.pkb
```

3. RESTful Service
```
@src/restful_service_onlyoffice_editor_callback.sql
```

OR

just import [apex/f170_onlyoffice_demo.sql](https://github.com/Dani3lSun/apex-onlyoffice-integration/blob/master/apex/f170_onlyoffice_demo.sql) into your APEX workspace. This will install all database objects into your parsing schema.


## Installation ONLYOFFICE Server

[DocumentServer](https://github.com/ONLYOFFICE/DocumentServer)
[ONLYOFFICE Editor API](https://api.onlyoffice.com/editors/basic)
[Homepage](https://www.onlyoffice.com/)

```
# Insstall with Docker and listening on port 8181
docker run -i -t -d -p 8181:80 --name onlyoffice-documentserver --restart=always onlyoffice/documentserver
# disable editor plugins
docker exec -it onlyoffice-documentserver /bin/bash

cd /var/www/onlyoffice/documentserver/sdkjs-plugins
mv cbr/config.json cbr/config.json.old
mv chess/config.json chess/config.json.old
mv clipart/config.json clipart/config.json.old
mv helloworld/config.json helloworld/config.json.old
mv ocr/config.json ocr/config.json.old
mv photoeditor/config.json photoeditor/config.json.old
mv speech/config.json speech/config.json.old
mv templates/config.json templates/config.json.old
mv youtube/config.json youtube/config.json.old
```


## License

[MIT License](https://github.com/Dani3lSun/apex-onlyoffice-integration/blob/master/LICENSE)

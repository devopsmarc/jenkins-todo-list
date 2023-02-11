# django-todolist

Simple todolist write in django for general use and pipeline automation..

  - Be kind with my baby

### Quick and free tip:

> With great power comes great responsibility


### Tech

Dillinger uses a number of open source projects to work properly:

* [Django] - Django makes it easier to build better Web apps more quickly and with less code.
* [Python-Venv] - The venv module provides support for creating lightweight “virtual environments” with their own site directories
* [MySQL] - MySQL is an Oracle-backed open source relational database management system (RDBMS) based on Structured Query Language (SQL).


### Installation

Install the dependencies and start the server.

```sh
$ cd django-todolist
$ pip install -r requirements.txt
$ python manage.py migrate # Running the migrations
$ python manage.py createsuperuser # Create a superuser
$ python manage.py runserver
```


License
----

GPL

### Jenkins Pipeline - Console Output
Started by upstream project "jenkins-todo-list-principal" build number 5
originally caused by:
 Started by an SCM change
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/todo-list-desenvolvimento
[Pipeline] {
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Point to dev Config File)
[Pipeline] configFileProvider
provisioning config files...
copy managed file [.env-dev] to file:/var/lib/jenkins/workspace/todo-list-desenvolvimento@tmp/config2123328669636102296tmp
[Pipeline] {
[Pipeline] sh
+ cat /var/lib/jenkins/workspace/todo-list-desenvolvimento@tmp/config2123328669636102296tmp
[Pipeline] }
Deleting 1 temporary files
[Pipeline] // configFileProvider
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Remove existing container)
[Pipeline] script
[Pipeline] {
[Pipeline] sh
+ docker rm -f django-todolist-dev
django-todolist-dev
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Run new container)
[Pipeline] script
[Pipeline] {
[Pipeline] sh
+ docker run -d -p 81:8000 -v /var/run/mysqld/mysqld.sock:/var/run/mysqld/mysqld.sock -v /var/lib/jenkins/workspace/todo-list-desenvolvimento/.env:/usr/src/app/to_do/.env --name=django-todolist-dev devopsmarc/django_todolist_image_build:latest
a90e40cde7a37a8e13e5cd431d9897f0c809f4ca9510842cdfc328b639b3d4df
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Message user)
[Pipeline] slackSend
Slack Send Pipeline step running, values are - baseUrl: <empty>, teamDomain: devopsmarc, channel: pipeline-todolist, color: good, botUser: false, tokenCredentialId: slack-token, notifyCommitters: false, iconEmoji: <empty>, username: <empty>, timestamp: <empty>
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to production?)
[Pipeline] script
[Pipeline] {
[Pipeline] slackSend
Slack Send Pipeline step running, values are - baseUrl: <empty>, teamDomain: devopsmarc, channel: pipeline-todolist, color: warning, botUser: false, tokenCredentialId: slack-token, notifyCommitters: false, iconEmoji: <empty>, username: <empty>, timestamp: <empty>
[Pipeline] timeout
Timeout set to expire in 10 min
[Pipeline] {
[Pipeline] input
Deploy to production?
Deploy or Abort
Approved by devopsmarc
[Pipeline] }
[Pipeline] // timeout
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (deploy)
[Pipeline] script
[Pipeline] {
[Pipeline] build (Building todo-list-producao)
Scheduling project: todo-list-producao
Starting building: todo-list-producao #2
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS

### Sonarqube Scanner
Started by user Aluno Alura
Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/todo-list-sonarqube
[WS-CLEANUP] Deleting project workspace...
[WS-CLEANUP] Deferred wipeout is used...
[WS-CLEANUP] Done
The recommended git tool is: NONE
using credential github-ssh
Cloning the remote Git repository
Cloning repository git@github.com:devopsmarc/jenkins-todo-list.git
 > git init /var/lib/jenkins/workspace/todo-list-sonarqube # timeout=10
Fetching upstream changes from git@github.com:devopsmarc/jenkins-todo-list.git
 > git --version # timeout=10
 > git --version # 'git version 2.17.1'
using GIT_SSH to set credentials github-ssh
Verifying host key using known hosts file, will automatically accept unseen keys
 > git fetch --tags --progress -- git@github.com:devopsmarc/jenkins-todo-list.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url git@github.com:devopsmarc/jenkins-todo-list.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision d6537c8c088f3e7a84bbcbc766492d9aef5dcd96 (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f d6537c8c088f3e7a84bbcbc766492d9aef5dcd96 # timeout=10
Commit message: ""Changed Log In button""
 > git rev-list --no-walk d6537c8c088f3e7a84bbcbc766492d9aef5dcd96 # timeout=10
[todo-list-sonarqube] $ /bin/bash /tmp/jenkins12809737534668284333.sh
--2023-02-11 18:43:52--  https://s3.amazonaws.com/caelum-online-public/1110-jenkins/05/sonar-scanner-cli-3.3.0.1492-linux.zip
Resolving s3.amazonaws.com (s3.amazonaws.com)... 52.216.28.174, 52.216.101.125, 52.216.136.133, ...
Connecting to s3.amazonaws.com (s3.amazonaws.com)|52.216.28.174|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73866903 (70M) [application/zip]
Saving to: ‘sonar-scanner-cli-3.3.0.1492-linux.zip’

     0K .......... .......... .......... .......... ..........  0%  483K 2m29s
    50K .......... .......... .......... .......... ..........  0%  414K 2m42s
   100K .......... .......... .......... .......... ..........  0%  413K 2m46s
   150K .......... .......... .......... .......... ..........  0% 73.4M 2m5s
   200K .......... .......... .......... .......... ..........  0% 52.8M 1m40s
   250K .......... .......... .......... .......... ..........  0%  435K 1m51s
   300K .......... .......... .......... .......... ..........  0% 23.7M 95s
   350K .......... .......... .......... .......... ..........  0% 7.28M 84s
   400K .......... .......... .......... .......... ..........  0% 34.7M 75s
   450K .......... .......... .......... .......... ..........  0% 37.3M 68s
   500K .......... .......... .......... .......... ..........  0%  466K 76s
   550K .......... .......... .......... .......... ..........  0% 10.2M 70s
   600K .......... .......... .......... .......... ..........  0% 15.1M 65s
   650K .......... .......... .......... .......... ..........  0% 79.5M 60s
   700K .......... .......... .......... .......... ..........  1% 90.0M 56s
71400K .......... .......... .......... .......... .......... 99% 20.1M 0s
 71450K .......... .......... .......... .......... .......... 99% 18.0M 0s
 71500K .......... .......... .......... .......... .......... 99% 2.84M 0s
 71550K .......... .......... .......... .......... .......... 99% 8.66M 0s
 71600K .......... .......... .......... .......... .......... 99% 22.1M 0s
 71650K .......... .......... .......... .......... .......... 99% 19.3M 0s
 71700K .......... .......... .......... .......... .......... 99% 29.0M 0s
 71750K .......... .......... .......... .......... .......... 99% 23.0M 0s
 71800K .......... .......... .......... .......... .......... 99% 17.0M 0s
 71850K .......... .......... .......... .......... .......... 99% 26.1M 0s
 71900K .......... .......... .......... .......... .......... 99% 28.3M 0s
 71950K .......... .......... .......... .......... .......... 99% 25.5M 0s
 72000K .......... .......... .......... .......... .......... 99% 32.1M 0s
 72050K .......... .......... .......... .......... .......... 99% 27.4M 0s
 72100K .......... .......... .......... .....                100% 37.8M=11s

2023-02-11 18:44:04 (6.16 MB/s) - ‘sonar-scanner-cli-3.3.0.1492-linux.zip’ saved [73866903/73866903]

Archive:  sonar-scanner-cli-3.3.0.1492-linux.zip
   creating: sonar-scanner-3.3.0.1492-linux/
   creating: sonar-scanner-3.3.0.1492-linux/jre/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko.UTF-8/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko.UTF-8/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/pt_BR/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/pt_BR/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/de/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/de/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/sv/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/sv/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh.GBK/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh.GBK/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/it/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/it/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_HK.BIG5HK/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_HK.BIG5HK/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/es/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/es/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ja/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ja/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/fr/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/fr/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW.BIG5/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW.BIG5/LC_MESSAGES/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/applet/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/jfr/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/management/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/jli/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/
   creating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/
   creating: sonar-scanner-3.3.0.1492-linux/jre/bin/
   creating: sonar-scanner-3.3.0.1492-linux/lib/
   creating: sonar-scanner-3.3.0.1492-linux/conf/
   creating: sonar-scanner-3.3.0.1492-linux/bin/
  inflating: sonar-scanner-3.3.0.1492-linux/jre/Welcome.html  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/LICENSE  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/COPYRIGHT  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/THIRDPARTYLICENSEREADME-JAVAFX.txt  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.11.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.5.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jfr.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.6.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jvm.hprof.txt  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/charsets.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.11.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jexec  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jfxswt.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/psfontj2d.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko.UTF-8/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/pt_BR/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/de/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/sv/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh.GBK/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/it/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_HK.BIG5HK/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/es/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ja/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/fr/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW.BIG5/LC_MESSAGES/sunw_java_plugin.mo  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jfr/profile.jfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jfr/default.jfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/resources.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/management/jmxremote.access  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/management/jmxremote.password.template  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/management/management.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/management/snmp.acl.template  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/hijrah-config-umalqura.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/currency.data  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/content-types.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/logging.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/flavormap.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/fonts.dir  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaSansDemiOblique.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaTypewriterOblique.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaSansOblique.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaTypewriterBoldOblique.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/calendars.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.6.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/javaws.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/sound.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_CN.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_HK.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_sv.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/MixedCodeMainDialogJs.ui  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/mixcode_s.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/ffjcext.zip  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_ja.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_TW.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash_11@2x-lic.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_pt_BR.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_es.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_ko.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash@2x.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/MixedCodeMainDialog.ui  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_de.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_fr.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_it.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/java-icon.ico  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash_11-lic.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/cautionshield.icns  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/javafx.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/blacklisted.certs  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/java.security  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/blacklist  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/cacerts  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/java.policy  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/US_export_policy.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/trusted.libraries  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/javaws.policy  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/security/local_policy.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjava.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libfontmanager.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libglass.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjpeg.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libzip.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjawt.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/libjsig.so  -> ../libjsig.so 
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/libjvm.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/Xusage.txt  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjdwp.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libmlib_image.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_pango.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_common.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsplashscreen.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libbci.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libkcms.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsound.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libhprof.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_es2.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdeploy.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsunec.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdecora_sse.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libt2k.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libverify.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsig.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libresource.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdt_socket.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfxmedia.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjava_crw_demo.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-53.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-54.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnio.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjaas_unix.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdcpr.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libmanagement.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-56.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/jli/libjli.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_iio.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnpjp2.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnpt.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/jvm.cfg  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-ffmpeg-56.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2pcsc.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsdt.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfxwebkit.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/release  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/README  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.10.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/management-agent.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.Turbo.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/classlist  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/net.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.Turbo.bfc  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/psfont.properties.ja  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/tzdb.dat  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/plugin.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/rt.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsctp.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libinstrument.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsoundalsa.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt_xawt.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_t2k.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libgstreamer-lite.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_sw.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/liblcms.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt_headless.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnet.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_freetype.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2pkcs11.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libunpack.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libfxplugins.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfr.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2gss.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-55.so  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunpkcs11.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/cldrdata.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/dnsns.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/jaccess.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunec.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/zipfs.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/localedata.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/nashorn.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunjce_provider.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/jfxrt.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/ext/meta-index  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/LINEAR_RGB.pf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/CIEXYZ.pf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/sRGB.pf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/PYCC.pf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/GRAY.pf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/fonts.dir  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightDemiItalic.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaTypewriterBold.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightRegular.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightDemiBold.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightItalic.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaSansDemiBold.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaTypewriterRegular.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaSansRegular.ttf  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.10.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jce.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/jsse.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/meta-index  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-application-x-java-archive.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-text-x-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-jcontrol.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-javaws.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun-javaws.desktop  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun_java.desktop  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun-java.desktop  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.5.properties.src  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_LinkNoDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_MoveNoDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_CopyDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/cursors.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_LinkDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_CopyNoDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_MoveDrop32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/invalid32x32.gif  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_HighContrastInverse.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_HighContrast.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_LowContrast.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java.png  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/THIRDPARTYLICENSEREADME.txt  
  inflating: sonar-scanner-3.3.0.1492-linux/jre/bin/java  
  inflating: sonar-scanner-3.3.0.1492-linux/lib/sonar-scanner-cli-3.3.0.1492.jar  
  inflating: sonar-scanner-3.3.0.1492-linux/conf/sonar-scanner.properties  
  inflating: sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner-debug  
  inflating: sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner  
finishing deferred symbolic links:
  sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/libjsig.so -> ../libjsig.so
18:44:15.826 INFO: Scanner configuration file: /var/lib/jenkins/workspace/todo-list-sonarqube/sonar-scanner-3.3.0.1492-linux/conf/sonar-scanner.properties
18:44:15.863 INFO: Project root configuration file: NONE
18:44:15.950 INFO: SonarQube Scanner 3.3.0.1492
18:44:15.950 INFO: Java 1.8.0_121 Oracle Corporation (64-bit)
18:44:15.950 INFO: Linux 4.15.0-202-generic amd64
18:44:16.686 DEBUG: keyStore is : 
18:44:16.686 DEBUG: keyStore type is : jks
18:44:16.687 DEBUG: keyStore provider is : 
18:44:16.687 DEBUG: init keystore
18:44:16.692 DEBUG: init keymanager of type SunX509
18:44:17.368 DEBUG: Create: /var/lib/jenkins/.sonar/cache
18:44:17.373 INFO: User cache: /var/lib/jenkins/.sonar/cache
18:44:17.373 DEBUG: Create: /var/lib/jenkins/.sonar/cache/_tmp
18:44:17.378 DEBUG: Extract sonar-scanner-api-batch in temp...
18:44:17.427 DEBUG: Get bootstrap index...
18:44:17.427 DEBUG: Download: http://192.168.15.20:9000/batch/index
18:44:17.653 DEBUG: Get bootstrap completed
18:44:17.717 DEBUG: Download http://192.168.15.20:9000/batch/file?name=sonar-scanner-engine-shaded-6.7.7.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache8049315755962543980.tmp
18:44:19.281 DEBUG: Create isolated classloader...
18:44:19.374 DEBUG: Start temp cleaning...
18:44:19.411 DEBUG: Temp cleaning done
18:44:19.411 DEBUG: Execution getVersion
18:44:19.413 INFO: SonarQube server 6.7.7
18:44:19.415 INFO: Default locale: "en", source code encoding: "UTF-8" (analysis is platform dependent)
18:44:19.416 DEBUG: Work directory: /var/lib/jenkins/workspace/todo-list-sonarqube/.scannerwork
18:44:19.418 DEBUG: Execution execute
18:44:19.868 INFO: Publish mode
18:44:19.991 INFO: Load global settings
18:44:20.839 DEBUG: GET 200 http://192.168.15.20:9000/api/settings/values.protobuf | time=829ms
18:44:20.855 INFO: Load global settings (done) | time=863ms
18:44:20.866 INFO: Server id: BF41A1F2-AYZBtXgHmTp3KIuR9tRf
18:44:20.886 INFO: User cache: /var/lib/jenkins/.sonar/cache
18:44:22.602 INFO: Load plugins index
18:44:22.684 DEBUG: GET 200 http://192.168.15.20:9000/api/plugins/installed | time=82ms
18:44:23.187 INFO: Load plugins index (done) | time=585ms
18:44:23.187 DEBUG: Load plugins
18:44:23.190 DEBUG: Download plugin sonar-flex-plugin-2.3.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache8715465523799746403.tmp
18:44:23.216 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/flex/sonar-flex-plugin-2.3.jar | time=26ms
18:44:23.413 DEBUG: Download plugin sonar-csharp-plugin-6.5.0.3766.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache6387790072852007146.tmp
18:44:23.416 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/csharp/sonar-csharp-plugin-6.5.0.3766.jar | time=3ms
18:44:23.463 DEBUG: Download plugin sonar-javascript-plugin-3.2.0.5506.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache954539988005863438.tmp
18:44:23.476 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/javascript/sonar-javascript-plugin-3.2.0.5506.jar | time=12ms
18:44:23.546 DEBUG: Download plugin sonar-java-plugin-4.15.0.12310.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache79869928652690232.tmp
18:44:23.549 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/java/sonar-java-plugin-4.15.0.12310.jar | time=3ms
18:44:23.674 DEBUG: Download plugin sonar-php-plugin-2.11.0.2485.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache5602142495386791923.tmp
18:44:23.677 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/php/sonar-php-plugin-2.11.0.2485.jar | time=3ms
18:44:23.793 DEBUG: Download plugin sonar-python-plugin-1.8.0.1496.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache1195466729435085229.tmp
18:44:23.796 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/python/sonar-python-plugin-1.8.0.1496.jar | time=3ms
18:44:23.896 DEBUG: Download plugin sonar-scm-git-plugin-1.3.0.869.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache6224832403151583121.tmp
18:44:23.900 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/scmgit/sonar-scm-git-plugin-1.3.0.869.jar | time=4ms
18:44:23.966 DEBUG: Download plugin sonar-scm-svn-plugin-1.6.0.860.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache6834953462044444403.tmp
18:44:23.972 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/scmsvn/sonar-scm-svn-plugin-1.6.0.860.jar | time=5ms
18:44:24.352 DEBUG: Download plugin sonar-typescript-plugin-1.1.0.1079.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache5637872555063176623.tmp
18:44:24.355 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/typescript/sonar-typescript-plugin-1.1.0.1079.jar | time=3ms
18:44:24.488 DEBUG: Download plugin sonar-xml-plugin-1.4.3.1027.jar to /var/lib/jenkins/.sonar/cache/_tmp/fileCache6570990007500368340.tmp
18:44:24.493 DEBUG: GET 200 http://192.168.15.20:9000/deploy/plugins/xml/sonar-xml-plugin-1.4.3.1027.jar | time=4ms
18:44:24.785 DEBUG: Load plugins (done) | time=1598ms
18:44:27.141 DEBUG: Plugins:
18:44:27.142 DEBUG:   * SonarC# 6.5.0.3766 (csharp)
18:44:27.142 DEBUG:   * SonarPython 1.8.0.1496 (python)
18:44:27.142 DEBUG:   * SonarJava 4.15.0.12310 (java)
18:44:27.142 DEBUG:   * Flex 2.3 (flex)
18:44:27.142 DEBUG:   * SonarQube :: Plugins :: SCM :: Git 1.3.0.869 (scmgit)
18:44:27.142 DEBUG:   * SonarXML 1.4.3.1027 (xml)
18:44:27.142 DEBUG:   * SonarPHP 2.11.0.2485 (php)
18:44:27.142 DEBUG:   * SonarTS 1.1.0.1079 (typescript)
18:44:27.142 DEBUG:   * SonarQube :: Plugins :: SCM :: SVN 1.6.0.860 (scmsvn)
18:44:27.142 DEBUG:   * SonarJS 3.2.0.5506 (javascript)
18:44:30.258 INFO: Process project properties
18:44:30.281 DEBUG: Process project properties (done) | time=24ms
18:44:30.486 INFO: Load project repositories
18:44:30.800 DEBUG: GET 200 http://192.168.15.20:9000/batch/project.protobuf?key=jenkins-todolist | time=310ms
18:44:31.070 INFO: Load project repositories (done) | time=584ms
18:44:31.229 DEBUG: Available languages:
18:44:31.229 DEBUG:   * C# => "cs"
18:44:31.229 DEBUG:   * Python => "py"
18:44:31.230 DEBUG:   * Java => "java"
18:44:31.230 DEBUG:   * Flex => "flex"
18:44:31.230 DEBUG:   * XML => "xml"
18:44:31.230 DEBUG:   * PHP => "php"
18:44:31.230 DEBUG:   * TypeScript => "ts"
18:44:31.230 DEBUG:   * JavaScript => "js"
18:44:31.254 INFO: Load quality profiles
18:44:31.590 DEBUG: GET 200 http://192.168.15.20:9000/api/qualityprofiles/search.protobuf?projectKey=jenkins-todolist | time=335ms
18:44:31.731 INFO: Load quality profiles (done) | time=477ms
18:44:31.837 INFO: Load active rules
18:44:33.891 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtfhYmTp3KIuR9tr4&p=1&ps=500 | time=2050ms
18:44:34.897 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtfo0mTp3KIuR9tzY&p=1&ps=500 | time=759ms
18:44:35.368 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtftCmTp3KIuR9t46&p=1&ps=500 | time=426ms
18:44:35.416 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtfvYmTp3KIuR9t55&p=1&ps=500 | time=21ms
18:44:35.549 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtfz9mTp3KIuR9t-k&p=1&ps=500 | time=132ms
18:44:35.608 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtf2dmTp3KIuR9uAj&p=1&ps=500 | time=56ms
18:44:35.705 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtf9EmTp3KIuR9uDU&p=1&ps=500 | time=84ms
18:44:35.743 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/search.protobuf?f=repo,name,severity,lang,internalKey,templateKey,params,actives,createdAt&activation=true&qprofile=AYZBtgAQmTp3KIuR9uEY&p=1&ps=500 | time=32ms
18:44:35.775 INFO: Load active rules (done) | time=3937ms
18:44:35.778 INFO: Load metrics repository
18:44:35.854 DEBUG: GET 200 http://192.168.15.20:9000/api/metrics/search?f=name,description,direction,qualitative,custom&ps=500&p=1 | time=75ms
18:44:35.961 INFO: Load metrics repository (done) | time=183ms
18:44:36.095 INFO: Project key: jenkins-todolist
18:44:36.095 DEBUG: Start recursive analysis of project modules
18:44:36.097 INFO: -------------  Scan jenkins-todolist
18:44:38.416 INFO: Load server rules
18:44:38.899 DEBUG: GET 200 http://192.168.15.20:9000/api/rules/list.protobuf | time=482ms
18:44:39.051 INFO: Load server rules (done) | time=635ms
18:44:39.338 INFO: Base dir: /var/lib/jenkins/workspace/todo-list-sonarqube
18:44:39.338 INFO: Working dir: /var/lib/jenkins/workspace/todo-list-sonarqube/.scannerwork
18:44:39.349 INFO: Source paths: .
18:44:39.350 INFO: Source encoding: UTF-8, default locale: en
18:44:41.206 DEBUG: Declared extensions of language C# were converted to sonar.lang.patterns.cs : **/*.cs
18:44:41.206 DEBUG: Declared extensions of language Python were converted to sonar.lang.patterns.py : **/*.py
18:44:41.206 DEBUG: Declared extensions of language Java were converted to sonar.lang.patterns.java : **/*.java,**/*.jav
18:44:41.206 DEBUG: Declared extensions of language Flex were converted to sonar.lang.patterns.flex : **/*.as
18:44:41.207 DEBUG: Declared extensions of language XML were converted to sonar.lang.patterns.xml : **/*.xml,**/*.xsd,**/*.xsl
18:44:41.207 DEBUG: Declared extensions of language PHP were converted to sonar.lang.patterns.php : **/*.php,**/*.php3,**/*.php4,**/*.php5,**/*.phtml,**/*.inc
18:44:41.208 DEBUG: Declared extensions of language TypeScript were converted to sonar.lang.patterns.ts : **/*.ts,**/*.tsx
18:44:41.208 DEBUG: Declared extensions of language JavaScript were converted to sonar.lang.patterns.js : **/*.js,**/*.jsx,**/*.vue
18:44:41.214 DEBUG: Initializers : 
18:44:41.277 INFO: Index files
18:44:41.388 DEBUG: 'sonar-scanner-cli-3.3.0.1492-linux.zip' indexed with language 'null'
18:44:41.390 DEBUG: 'to_do/urls.py' indexed with language 'py'
18:44:41.391 DEBUG: 'to_do/__init__.py' indexed with language 'py'
18:44:41.392 DEBUG: 'to_do/wsgi.py' indexed with language 'py'
18:44:41.393 DEBUG: 'to_do/settings.py' indexed with language 'py'
18:44:41.394 DEBUG: 'core/tests.py' indexed with language 'py'
18:44:41.394 DEBUG: 'core/views.py' indexed with language 'py'
18:44:41.394 DEBUG: 'core/urls.py' indexed with language 'py'
18:44:41.395 DEBUG: 'core/forms.py' indexed with language 'py'
18:44:41.395 DEBUG: 'core/models.py' indexed with language 'py'
18:44:41.395 DEBUG: 'core/__init__.py' indexed with language 'py'
18:44:41.396 DEBUG: 'core/apps.py' indexed with language 'py'
18:44:41.396 DEBUG: 'core/admin.py' indexed with language 'py'
18:44:41.396 DEBUG: 'core/migrations/0001_initial.py' indexed with language 'py'
18:44:41.397 DEBUG: 'core/migrations/__init__.py' indexed with language 'py'
18:44:41.397 DEBUG: 'core/migrations/0004_auto_20190321_2123.py' indexed with language 'py'
18:44:41.397 DEBUG: 'core/migrations/0002_todo_completed_at.py' indexed with language 'py'
18:44:41.398 DEBUG: 'core/migrations/0005_auto_20190325_2322.py' indexed with language 'py'
18:44:41.398 DEBUG: 'core/migrations/0003_auto_20190307_1500.py' indexed with language 'py'
18:44:41.398 DEBUG: 'core/templates/core/base.html' indexed with language 'null'
18:44:41.399 DEBUG: 'core/templates/core/index.html' indexed with language 'null'
18:44:41.399 DEBUG: 'core/templates/core/new.html' indexed with language 'null'
18:44:41.399 DEBUG: 'sonar-scanner-3.3.0.1492-linux/conf/sonar-scanner.properties' indexed with language 'null'
18:44:41.400 DEBUG: 'sonar-scanner-3.3.0.1492-linux/lib/sonar-scanner-cli-3.3.0.1492.jar' indexed with language 'null'
18:44:41.400 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/LICENSE' indexed with language 'null'
18:44:41.417 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/currency.data' indexed with language 'null'
18:44:41.418 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightItalic.ttf' indexed with language 'null'
18:44:41.420 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaTypewriterRegular.ttf' indexed with language 'null'
18:44:41.420 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightDemiItalic.ttf' indexed with language 'null'
18:44:41.421 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/fonts.dir' indexed with language 'null'
18:44:41.422 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaSansRegular.ttf' indexed with language 'null'
18:44:41.423 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightRegular.ttf' indexed with language 'null'
18:44:41.424 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaTypewriterBold.ttf' indexed with language 'null'
18:44:41.425 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaSansDemiBold.ttf' indexed with language 'null'
18:44:41.427 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fonts/LucidaBrightDemiBold.ttf' indexed with language 'null'
18:44:41.428 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.5.properties.src' indexed with language 'null'
18:44:41.428 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jsse.jar' indexed with language 'null'
18:44:41.429 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.Turbo.bfc' indexed with language 'null'
18:44:41.430 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jfr/default.jfc' indexed with language 'null'
18:44:41.431 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jfr/profile.jfc' indexed with language 'null'
18:44:41.431 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/sound.properties' indexed with language 'null'
18:44:41.432 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.bfc' indexed with language 'null'
18:44:41.432 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/rt.jar' indexed with language 'null'
18:44:41.435 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/resources.jar' indexed with language 'null'
18:44:41.435 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/plugin.jar' indexed with language 'null'
18:44:41.437 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.438 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh.GBK/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.439 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_HK.BIG5HK/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.440 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ja/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.440 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW.BIG5/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.441 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/it/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.442 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/pt_BR/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.443 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/zh_TW/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.444 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/sv/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.445 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko.UTF-8/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.446 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/de/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.446 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/ko/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.447 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/es/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.447 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/locale/fr/LC_MESSAGES/sunw_java_plugin.mo' indexed with language 'null'
18:44:41.448 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-55.so' indexed with language 'null'
18:44:41.449 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libkcms.so' indexed with language 'null'
18:44:41.450 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libinstrument.so' indexed with language 'null'
18:44:41.450 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font.so' indexed with language 'null'
18:44:41.451 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libt2k.so' indexed with language 'null'
18:44:41.452 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_iio.so' indexed with language 'null'
18:44:41.453 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdecora_sse.so' indexed with language 'null'
18:44:41.453 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjawt.so' indexed with language 'null'
18:44:41.454 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libresource.so' indexed with language 'null'
18:44:41.454 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2pcsc.so' indexed with language 'null'
18:44:41.454 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/Xusage.txt' indexed with language 'null'
18:44:41.455 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/libjsig.so' indexed with language 'null'
18:44:41.455 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/server/libjvm.so' indexed with language 'null'
18:44:41.455 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsoundalsa.so' indexed with language 'null'
18:44:41.456 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/jvm.cfg' indexed with language 'null'
18:44:41.456 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnet.so' indexed with language 'null'
18:44:41.457 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjpeg.so' indexed with language 'null'
18:44:41.458 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsound.so' indexed with language 'null'
18:44:41.458 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdeploy.so' indexed with language 'null'
18:44:41.460 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_t2k.so' indexed with language 'null'
18:44:41.460 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsunec.so' indexed with language 'null'
18:44:41.461 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libfontmanager.so' indexed with language 'null'
18:44:41.462 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libunpack.so' indexed with language 'null'
18:44:41.463 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfxwebkit.so' indexed with language 'null'
18:44:41.463 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt_xawt.so' indexed with language 'null'
18:44:41.463 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2pkcs11.so' indexed with language 'null'
18:44:41.464 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libgstreamer-lite.so' indexed with language 'null'
18:44:41.464 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libverify.so' indexed with language 'null'
18:44:41.464 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_sw.so' indexed with language 'null'
18:44:41.464 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libbci.so' indexed with language 'null'
18:44:41.465 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjava.so' indexed with language 'null'
18:44:41.465 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libj2gss.so' indexed with language 'null'
18:44:41.465 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsctp.so' indexed with language 'null'
18:44:41.465 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt.so' indexed with language 'null'
18:44:41.466 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_freetype.so' indexed with language 'null'
18:44:41.466 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libhprof.so' indexed with language 'null'
18:44:41.466 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libawt_headless.so' indexed with language 'null'
18:44:41.467 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjdwp.so' indexed with language 'null'
18:44:41.467 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjaas_unix.so' indexed with language 'null'
18:44:41.467 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-53.so' indexed with language 'null'
18:44:41.468 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnpt.so' indexed with language 'null'
18:44:41.468 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/liblcms.so' indexed with language 'null'
18:44:41.468 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnio.so' indexed with language 'null'
18:44:41.468 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjavafx_font_pango.so' indexed with language 'null'
18:44:41.469 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfr.so' indexed with language 'null'
18:44:41.469 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-ffmpeg-56.so' indexed with language 'null'
18:44:41.469 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libmlib_image.so' indexed with language 'null'
18:44:41.469 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdcpr.so' indexed with language 'null'
18:44:41.470 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-54.so' indexed with language 'null'
18:44:41.470 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjfxmedia.so' indexed with language 'null'
18:44:41.470 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsig.so' indexed with language 'null'
18:44:41.471 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libmanagement.so' indexed with language 'null'
18:44:41.471 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libglass.so' indexed with language 'null'
18:44:41.471 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libzip.so' indexed with language 'null'
18:44:41.471 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libnpjp2.so' indexed with language 'null'
18:44:41.472 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjsdt.so' indexed with language 'null'
18:44:41.472 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libfxplugins.so' indexed with language 'null'
18:44:41.472 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/jli/libjli.so' indexed with language 'null'
18:44:41.473 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libjava_crw_demo.so' indexed with language 'null'
18:44:41.473 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libavplugin-56.so' indexed with language 'null'
18:44:41.473 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libsplashscreen.so' indexed with language 'null'
18:44:41.474 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_common.so' indexed with language 'null'
18:44:41.474 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libdt_socket.so' indexed with language 'null'
18:44:41.475 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/amd64/libprism_es2.so' indexed with language 'null'
18:44:41.475 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/management-agent.jar' indexed with language 'null'
18:44:41.475 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/tzdb.dat' indexed with language 'null'
18:44:41.476 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/blacklisted.certs' indexed with language 'null'
18:44:41.477 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/java.security' indexed with language 'null'
18:44:41.477 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/blacklist' indexed with language 'null'
18:44:41.477 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/US_export_policy.jar' indexed with language 'null'
18:44:41.478 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/local_policy.jar' indexed with language 'null'
18:44:41.478 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/trusted.libraries' indexed with language 'null'
18:44:41.478 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/javaws.policy' indexed with language 'null'
18:44:41.479 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/java.policy' indexed with language 'null'
18:44:41.479 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/security/cacerts' indexed with language 'null'
18:44:41.479 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaSansOblique.ttf' indexed with language 'null'
18:44:41.480 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaSansDemiOblique.ttf' indexed with language 'null'
18:44:41.480 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaTypewriterOblique.ttf' indexed with language 'null'
18:44:41.480 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/fonts.dir' indexed with language 'null'
18:44:41.480 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/oblique-fonts/LucidaTypewriterBoldOblique.ttf' indexed with language 'null'
18:44:41.481 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.6.bfc' indexed with language 'null'
18:44:41.481 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/javaws.jar' indexed with language 'null'
18:44:41.481 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/javafx.properties' indexed with language 'null'
18:44:41.481 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/hijrah-config-umalqura.properties' indexed with language 'null'
18:44:41.482 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.11.bfc' indexed with language 'null'
18:44:41.482 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.5.bfc' indexed with language 'null'
18:44:41.482 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jexec' indexed with language 'null'
18:44:41.483 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.483 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-javaws.png' indexed with language 'null'
18:44:41.483 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/apps/sun-java.png' indexed with language 'null'
18:44:41.484 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.484 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.484 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/48x48/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.485 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.485 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-javaws.png' indexed with language 'null'
18:44:41.486 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/apps/sun-java.png' indexed with language 'null'
18:44:41.486 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.486 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.487 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrast/16x16/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.487 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.487 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-javaws.png' indexed with language 'null'
18:44:41.488 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/apps/sun-java.png' indexed with language 'null'
18:44:41.488 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.488 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.489 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/48x48/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.489 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.489 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-javaws.png' indexed with language 'null'
18:44:41.490 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/apps/sun-java.png' indexed with language 'null'
18:44:41.490 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.490 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.491 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/LowContrast/16x16/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.492 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.492 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-javaws.png' indexed with language 'null'
18:44:41.493 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/apps/sun-java.png' indexed with language 'null'
18:44:41.494 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.496 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.497 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/48x48/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.498 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.499 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-javaws.png' indexed with language 'null'
18:44:41.499 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/apps/sun-java.png' indexed with language 'null'
18:44:41.499 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.500 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.500 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/HighContrastInverse/16x16/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.500 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.501 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-javaws.png' indexed with language 'null'
18:44:41.501 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/apps/sun-java.png' indexed with language 'null'
18:44:41.501 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.502 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.502 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/48x48/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.502 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-jcontrol.png' indexed with language 'null'
18:44:41.503 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-javaws.png' indexed with language 'null'
18:44:41.503 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/apps/sun-java.png' indexed with language 'null'
18:44:41.503 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-text-x-java.png' indexed with language 'null'
18:44:41.504 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-application-x-java-jnlp-file.png' indexed with language 'null'
18:44:41.504 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/icons/hicolor/16x16/mimetypes/gnome-mime-application-x-java-archive.png' indexed with language 'null'
18:44:41.504 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml' indexed with language 'xml'
18:44:41.505 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml' indexed with language 'xml'
18:44:41.505 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun-javaws.desktop' indexed with language 'null'
18:44:41.505 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun_java.desktop' indexed with language 'null'
18:44:41.506 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/applications/sun-java.desktop' indexed with language 'null'
18:44:41.506 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/GRAY.pf' indexed with language 'null'
18:44:41.506 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/CIEXYZ.pf' indexed with language 'null'
18:44:41.507 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/LINEAR_RGB.pf' indexed with language 'null'
18:44:41.507 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/sRGB.pf' indexed with language 'null'
18:44:41.507 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/cmm/PYCC.pf' indexed with language 'null'
18:44:41.507 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.10.bfc' indexed with language 'null'
18:44:41.508 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jfr.jar' indexed with language 'null'
18:44:41.508 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_HighContrastInverse.png' indexed with language 'null'
18:44:41.509 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_LowContrast.png' indexed with language 'null'
18:44:41.509 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java.png' indexed with language 'null'
18:44:41.510 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/icons/sun-java_HighContrast.png' indexed with language 'null'
18:44:41.510 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_LinkDrop32x32.gif' indexed with language 'null'
18:44:41.510 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/invalid32x32.gif' indexed with language 'null'
18:44:41.511 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_LinkNoDrop32x32.gif' indexed with language 'null'
18:44:41.511 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_CopyNoDrop32x32.gif' indexed with language 'null'
18:44:41.511 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/cursors.properties' indexed with language 'null'
18:44:41.512 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_CopyDrop32x32.gif' indexed with language 'null'
18:44:41.512 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_MoveDrop32x32.gif' indexed with language 'null'
18:44:41.512 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/images/cursors/motif_MoveNoDrop32x32.gif' indexed with language 'null'
18:44:41.513 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/psfont.properties.ja' indexed with language 'null'
18:44:41.513 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.10.properties.src' indexed with language 'null'
18:44:41.513 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.SuSE.11.properties.src' indexed with language 'null'
18:44:41.514 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/meta-index' indexed with language 'null'
18:44:41.514 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy.jar' indexed with language 'null'
18:44:41.514 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/localedata.jar' indexed with language 'null'
18:44:41.514 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunec.jar' indexed with language 'null'
18:44:41.515 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunjce_provider.jar' indexed with language 'null'
18:44:41.515 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/jaccess.jar' indexed with language 'null'
18:44:41.515 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/meta-index' indexed with language 'null'
18:44:41.515 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/dnsns.jar' indexed with language 'null'
18:44:41.516 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/cldrdata.jar' indexed with language 'null'
18:44:41.516 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/sunpkcs11.jar' indexed with language 'null'
18:44:41.516 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/jfxrt.jar' indexed with language 'null'
18:44:41.516 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/zipfs.jar' indexed with language 'null'
18:44:41.517 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/ext/nashorn.jar' indexed with language 'null'
18:44:41.517 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jce.jar' indexed with language 'null'
18:44:41.517 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/ffjcext.zip' indexed with language 'null'
18:44:41.518 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_es.properties' indexed with language 'null'
18:44:41.518 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_ko.properties' indexed with language 'null'
18:44:41.518 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_de.properties' indexed with language 'null'
18:44:41.519 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/cautionshield.icns' indexed with language 'null'
18:44:41.519 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/MixedCodeMainDialog.ui' indexed with language 'null'
18:44:41.519 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_sv.properties' indexed with language 'null'
18:44:41.519 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/java-icon.ico' indexed with language 'null'
18:44:41.520 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_ja.properties' indexed with language 'null'
18:44:41.520 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/mixcode_s.png' indexed with language 'null'
18:44:41.520 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/MixedCodeMainDialogJs.ui' indexed with language 'null'
18:44:41.520 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_fr.properties' indexed with language 'null'
18:44:41.521 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash@2x.gif' indexed with language 'null'
18:44:41.521 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash.gif' indexed with language 'null'
18:44:41.521 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash_11@2x-lic.gif' indexed with language 'null'
18:44:41.522 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_HK.properties' indexed with language 'null'
18:44:41.522 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_TW.properties' indexed with language 'null'
18:44:41.522 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/splash_11-lic.gif' indexed with language 'null'
18:44:41.522 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_it.properties' indexed with language 'null'
18:44:41.523 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_pt_BR.properties' indexed with language 'null'
18:44:41.523 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages.properties' indexed with language 'null'
18:44:41.523 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/deploy/messages_zh_CN.properties' indexed with language 'null'
18:44:41.524 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/flavormap.properties' indexed with language 'null'
18:44:41.524 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.RedHat.6.properties.src' indexed with language 'null'
18:44:41.524 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/classlist' indexed with language 'null'
18:44:41.525 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/logging.properties' indexed with language 'null'
18:44:41.525 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jfxswt.jar' indexed with language 'null'
18:44:41.525 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/jvm.hprof.txt' indexed with language 'null'
18:44:41.526 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/content-types.properties' indexed with language 'null'
18:44:41.526 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/management/management.properties' indexed with language 'null'
18:44:41.527 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/management/snmp.acl.template' indexed with language 'null'
18:44:41.527 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/management/jmxremote.password.template' indexed with language 'null'
18:44:41.527 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/management/jmxremote.access' indexed with language 'null'
18:44:41.528 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/calendars.properties' indexed with language 'null'
18:44:41.528 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/charsets.jar' indexed with language 'null'
18:44:41.528 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/net.properties' indexed with language 'null'
18:44:41.528 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/psfontj2d.properties' indexed with language 'null'
18:44:41.529 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.properties.src' indexed with language 'null'
18:44:41.529 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/fontconfig.Turbo.properties.src' indexed with language 'null'
18:44:41.529 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/COPYRIGHT' indexed with language 'null'
18:44:41.529 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/Welcome.html' indexed with language 'null'
18:44:41.530 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/THIRDPARTYLICENSEREADME.txt' indexed with language 'null'
18:44:41.530 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/release' indexed with language 'null'
18:44:41.530 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/README' indexed with language 'null'
18:44:41.530 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/THIRDPARTYLICENSEREADME-JAVAFX.txt' indexed with language 'null'
18:44:41.531 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/bin/java' indexed with language 'null'
18:44:41.531 DEBUG: 'sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner-debug' indexed with language 'null'
18:44:41.531 DEBUG: 'sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner' indexed with language 'null'
18:44:41.531 DEBUG: 'manage.py' indexed with language 'py'
18:44:41.532 DEBUG: 'static/css/signin.css' indexed with language 'null'
18:44:41.532 DEBUG: 'README.md' indexed with language 'null'
18:44:41.532 DEBUG: 'requirements.txt' indexed with language 'null'
18:44:41.532 DEBUG: 'Dockerfile' indexed with language 'null'
18:44:41.532 DEBUG: 'templates/registration/login.html' indexed with language 'null'
18:44:41.533 INFO: 289 files indexed
18:44:41.574 INFO: Quality profile for py: Sonar way
18:44:41.574 INFO: Quality profile for xml: Sonar way
18:44:46.449 DEBUG: 'Generic Coverage Report' skipped because one of the required properties is missing
18:44:46.450 DEBUG: 'Generic Test Executions Report' skipped because one of the required properties is missing
18:44:46.451 DEBUG: 'C#' skipped because there is no related file in current project
18:44:46.452 DEBUG: 'C# Tests Coverage Report Import' skipped because there is no related file in current project
18:44:46.454 DEBUG: '[Deprecated] C# Integration Tests Coverage Report Import' skipped because there is no related file in current project
18:44:46.455 DEBUG: 'C# Unit Test Results Import' skipped because there is no related file in current project
18:44:46.455 DEBUG: 'SurefireSensor' skipped because there is no related file in current project
18:44:46.455 DEBUG: 'JaCoCoSensor' skipped because there is no related file in current project
18:44:46.456 DEBUG: 'JavaSquidSensor' skipped because there is no related file in current project
18:44:46.456 DEBUG: 'Flex' skipped because there is no related file in current project
18:44:46.456 DEBUG: 'Flex Cobertura' skipped because there is no related file in current project
18:44:46.457 DEBUG: 'PHP sensor' skipped because there is no related file in current project
18:44:46.463 DEBUG: 'TypeScript Sensor' skipped because there is no related file in current project
18:44:46.464 DEBUG: 'TypeScript LCOV Coverage Sensor' skipped because there is no related file in current project
18:44:46.464 DEBUG: 'JavaScript Squid Sensor' skipped because there is no related file in current project
18:44:46.669 DEBUG: 'Generic Coverage Report' skipped because one of the required properties is missing
18:44:46.669 DEBUG: 'Generic Test Executions Report' skipped because one of the required properties is missing
18:44:46.670 DEBUG: 'C#' skipped because there is no related file in current project
18:44:46.671 DEBUG: 'C# Tests Coverage Report Import' skipped because there is no related file in current project
18:44:46.671 DEBUG: '[Deprecated] C# Integration Tests Coverage Report Import' skipped because there is no related file in current project
18:44:46.671 DEBUG: 'C# Unit Test Results Import' skipped because there is no related file in current project
18:44:46.672 DEBUG: 'SurefireSensor' skipped because there is no related file in current project
18:44:46.675 DEBUG: 'JaCoCoSensor' skipped because there is no related file in current project
18:44:46.675 DEBUG: 'JavaSquidSensor' skipped because there is no related file in current project
18:44:46.675 DEBUG: 'Flex' skipped because there is no related file in current project
18:44:46.676 DEBUG: 'Flex Cobertura' skipped because there is no related file in current project
18:44:46.676 DEBUG: 'PHP sensor' skipped because there is no related file in current project
18:44:46.676 DEBUG: 'TypeScript Sensor' skipped because there is no related file in current project
18:44:46.676 DEBUG: 'TypeScript LCOV Coverage Sensor' skipped because there is no related file in current project
18:44:46.677 DEBUG: 'JavaScript Squid Sensor' skipped because there is no related file in current project
18:44:46.688 DEBUG: Sensors : PythonXUnitSensor -> Python Squid Sensor -> SonarJavaXmlFileSensor -> XML Sensor -> Analyzer for "php.ini" files -> Zero Coverage Sensor -> CPD Block Indexer
18:44:46.688 INFO: Sensor PythonXUnitSensor [python]
18:44:46.688 DEBUG: Using pattern 'xunit-reports/xunit-result-*.xml' to find reports
18:44:46.802 DEBUG: No report was found for sonar.python.xunit.reportPath using default pattern xunit-reports/xunit-result-*.xml
18:44:46.802 INFO: Sensor PythonXUnitSensor [python] (done) | time=114ms
18:44:46.802 INFO: Sensor Python Squid Sensor [python]
18:44:47.087 DEBUG: 'core/__init__.py' generated metadata  with charset 'UTF-8'
18:44:47.456 DEBUG: 'core/admin.py' generated metadata  with charset 'UTF-8'
18:44:47.741 DEBUG: 'core/apps.py' generated metadata  with charset 'UTF-8'
18:44:47.823 DEBUG: 'core/forms.py' generated metadata  with charset 'UTF-8'
18:44:47.841 DEBUG: 'core/migrations/0001_initial.py' generated metadata  with charset 'UTF-8'
18:44:47.864 DEBUG: 'core/migrations/0002_todo_completed_at.py' generated metadata  with charset 'UTF-8'
18:44:47.884 DEBUG: 'core/migrations/0003_auto_20190307_1500.py' generated metadata  with charset 'UTF-8'
18:44:47.903 DEBUG: 'core/migrations/0004_auto_20190321_2123.py' generated metadata  with charset 'UTF-8'
18:44:47.918 DEBUG: 'core/migrations/0005_auto_20190325_2322.py' generated metadata  with charset 'UTF-8'
18:44:47.924 DEBUG: 'core/migrations/__init__.py' generated metadata  with charset 'UTF-8'
18:44:47.936 DEBUG: 'core/models.py' generated metadata  with charset 'UTF-8'
18:44:47.997 DEBUG: 'core/tests.py' generated metadata  with charset 'UTF-8'
18:44:48.063 DEBUG: 'core/urls.py' generated metadata  with charset 'UTF-8'
18:44:48.088 DEBUG: 'core/views.py' generated metadata  with charset 'UTF-8'
18:44:48.101 DEBUG: 'manage.py' generated metadata  with charset 'UTF-8'
18:44:48.106 DEBUG: 'to_do/__init__.py' generated metadata  with charset 'UTF-8'
18:44:48.115 DEBUG: 'to_do/settings.py' generated metadata  with charset 'UTF-8'
18:44:48.161 DEBUG: 'to_do/urls.py' generated metadata  with charset 'UTF-8'
18:44:48.167 DEBUG: 'to_do/wsgi.py' generated metadata  with charset 'UTF-8'
18:44:48.185 INFO: Python unit test coverage
18:44:48.185 DEBUG: Using pattern 'coverage-reports/coverage-*.xml' to find reports
18:44:48.190 DEBUG: No report was found for sonar.python.coverage.reportPath using default pattern coverage-reports/coverage-*.xml
18:44:48.194 INFO: Python integration test coverage
18:44:48.194 DEBUG: Using pattern 'coverage-reports/it-coverage-*.xml' to find reports
18:44:48.201 DEBUG: No report was found for sonar.python.coverage.itReportPath using default pattern coverage-reports/it-coverage-*.xml
18:44:48.201 INFO: Python overall test coverage
18:44:48.201 DEBUG: Using pattern 'coverage-reports/overall-coverage-*.xml' to find reports
18:44:48.205 DEBUG: No report was found for sonar.python.coverage.overallReportPath using default pattern coverage-reports/overall-coverage-*.xml
18:44:48.205 INFO: Sensor Python Squid Sensor [python] (done) | time=1403ms
18:44:48.205 INFO: Sensor SonarJavaXmlFileSensor [java]
18:44:48.348 INFO: 2 source files to be analyzed
18:44:48.798 INFO: Sensor SonarJavaXmlFileSensor [java] (done) | time=593ms
18:44:48.798 INFO: 2/2 source files have been analyzed
18:44:48.799 INFO: Sensor XML Sensor [xml]
18:44:48.814 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml' generated metadata  with charset 'UTF-8'
18:44:48.816 DEBUG: Count lines in /var/lib/jenkins/workspace/todo-list-sonarqube/sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml
18:44:49.187 DEBUG: 'sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml' generated metadata  with charset 'UTF-8'
18:44:49.187 DEBUG: Count lines in /var/lib/jenkins/workspace/todo-list-sonarqube/sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml
18:44:49.194 INFO: Sensor XML Sensor [xml] (done) | time=396ms
18:44:49.195 INFO: Sensor Analyzer for "php.ini" files [php]
18:44:49.202 INFO: Sensor Analyzer for "php.ini" files [php] (done) | time=7ms
18:44:49.203 INFO: Sensor Zero Coverage Sensor
18:44:49.311 INFO: Sensor Zero Coverage Sensor (done) | time=109ms
18:44:49.312 INFO: Sensor CPD Block Indexer
18:44:49.312 DEBUG: org.sonar.scanner.cpd.deprecated.DefaultCpdBlockIndexer is used for py
18:44:49.326 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/__init__.py
18:44:49.332 DEBUG: Not enough content in 'core/__init__.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.332 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/admin.py
18:44:49.338 DEBUG: Not enough content in 'core/admin.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.339 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/apps.py
18:44:49.340 DEBUG: Not enough content in 'core/apps.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.340 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/forms.py
18:44:49.342 DEBUG: Not enough content in 'core/forms.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.342 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0001_initial.py
18:44:49.349 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0002_todo_completed_at.py
18:44:49.352 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0003_auto_20190307_1500.py
18:44:49.356 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0004_auto_20190321_2123.py
18:44:49.358 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0005_auto_20190325_2322.py
18:44:49.359 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/__init__.py
18:44:49.360 DEBUG: Not enough content in 'core/migrations/__init__.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.360 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/models.py
18:44:49.363 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/tests.py
18:44:49.365 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/urls.py
18:44:49.365 DEBUG: Not enough content in 'core/urls.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.367 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/core/views.py
18:44:49.368 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/manage.py
18:44:49.374 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/__init__.py
18:44:49.375 DEBUG: Not enough content in 'to_do/__init__.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.375 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/settings.py
18:44:49.382 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/urls.py
18:44:49.383 DEBUG: Populating index from /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/wsgi.py
18:44:49.384 DEBUG: Not enough content in 'to_do/wsgi.py' to have CPD blocks, it will not be part of the duplication detection
18:44:49.384 DEBUG: org.sonar.scanner.cpd.deprecated.DefaultCpdBlockIndexer is used for xml
18:44:49.384 DEBUG: No CpdMapping for language xml
18:44:49.384 INFO: Sensor CPD Block Indexer (done) | time=72ms
18:44:49.385 INFO: SCM provider for this project is: git
18:44:49.388 INFO: 18 files to be analyzed
18:44:49.507 DEBUG: readpipe [git, --version],/usr/bin
18:44:49.547 DEBUG: readpipe may return 'git version 2.17.1'
18:44:49.547 DEBUG: remaining output:

18:44:49.581 DEBUG: readpipe [git, config, --system, --edit],/usr/bin
18:44:49.623 DEBUG: readpipe may return '/etc/gitconfig'
18:44:49.624 DEBUG: remaining output:

18:44:49.707 DEBUG: Blame file core/migrations/0002_todo_completed_at.py
18:44:49.708 DEBUG: Blame file core/tests.py
18:44:49.952 DEBUG: Blame file core/migrations/0003_auto_20190307_1500.py
18:44:49.954 DEBUG: Blame file core/urls.py
18:44:50.051 DEBUG: Blame file core/views.py
18:44:50.053 DEBUG: Blame file core/migrations/0004_auto_20190321_2123.py
18:44:50.073 DEBUG: Blame file manage.py
18:44:50.080 DEBUG: Blame file core/migrations/0005_auto_20190325_2322.py
18:44:50.089 DEBUG: Blame file core/models.py
18:44:50.092 DEBUG: Blame file to_do/settings.py
18:44:50.106 DEBUG: Blame file core/admin.py
18:44:50.116 DEBUG: Blame file to_do/urls.py
18:44:50.117 DEBUG: Blame file core/apps.py
18:44:50.128 DEBUG: Blame file core/forms.py
18:44:50.128 DEBUG: Blame file to_do/wsgi.py
18:44:50.141 DEBUG: Blame file sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml
18:44:50.217 DEBUG: Blame file core/migrations/0001_initial.py
18:44:50.228 DEBUG: Unable to blame file sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml. No blame info at line 1. Is file committed? [Author: PersonIdent[Not Committed Yet, , Sat Feb 11 18:44:50 2023 +0000] Source commit: null]
18:44:50.228 DEBUG: Blame file sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml
18:44:50.229 DEBUG: Unable to blame file sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml. No blame info at line 1. Is file committed? [Author: PersonIdent[Not Committed Yet, , Sat Feb 11 18:44:50 2023 +0000] Source commit: null]
18:44:50.617 INFO: 16/18 files analyzed
18:44:50.617 WARN: Missing blame information for the following files:
18:44:50.617 WARN:   * sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-archive.xml
18:44:50.617 WARN:   * sonar-scanner-3.3.0.1492-linux/jre/lib/desktop/mime/packages/x-java-jnlp-file.xml
18:44:50.617 WARN: This may lead to missing/broken features in SonarQube
18:44:50.621 INFO: 8 files had no CPD blocks
18:44:50.621 INFO: Calculating CPD for 11 files
18:44:50.835 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/urls.py
18:44:50.877 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0004_auto_20190321_2123.py
18:44:50.878 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/to_do/settings.py
18:44:50.880 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0003_auto_20190307_1500.py
18:44:50.882 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/views.py
18:44:50.886 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0002_todo_completed_at.py
18:44:50.888 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/models.py
18:44:50.888 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0005_auto_20190325_2322.py
18:44:50.889 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/tests.py
18:44:50.890 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/core/migrations/0001_initial.py
18:44:50.890 DEBUG: Detection of duplications for /var/lib/jenkins/workspace/todo-list-sonarqube/manage.py
18:44:50.890 INFO: CPD calculation finished
18:44:51.123 INFO: Analysis report generated in 220ms, dir size=56 KB
18:44:51.199 INFO: Analysis reports compressed in 75ms, zip size=38 KB
18:44:51.199 INFO: Analysis report generated in /var/lib/jenkins/workspace/todo-list-sonarqube/.scannerwork/scanner-report
18:44:51.199 DEBUG: Upload report
18:44:51.513 DEBUG: POST 200 http://192.168.15.20:9000/api/ce/submit?projectKey=jenkins-todolist | time=300ms
18:44:51.555 INFO: Analysis report uploaded in 356ms
18:44:51.556 INFO: ANALYSIS SUCCESSFUL, you can browse http://192.168.15.20:9000/dashboard/index/jenkins-todolist
18:44:51.557 INFO: Note that you will be able to access the updated dashboard once the server has processed the submitted analysis report
18:44:51.557 INFO: More about the report processing at http://192.168.15.20:9000/api/ce/task?id=AYZBy1pemTp3KIuR9uHE
18:44:51.557 DEBUG: Report metadata written to /var/lib/jenkins/workspace/todo-list-sonarqube/.scannerwork/report-task.txt
18:44:51.558 DEBUG: Post-jobs : 
18:44:51.581 INFO: Task total time: 24.128 s
18:44:52.106 INFO: ------------------------------------------------------------------------
18:44:52.106 INFO: EXECUTION SUCCESS
18:44:52.106 INFO: ------------------------------------------------------------------------
18:44:52.106 INFO: Total time: 36.472s
18:44:52.211 INFO: Final Memory: 12M/104M
18:44:52.211 INFO: ------------------------------------------------------------------------
Finished: SUCCESS
http://www.gentoo-wiki.info/HOWTO_Installing_3rd_Party_Ebuilds

Example: Install `app-admin/filebeat-bin` from Gentoo portage

1) Create the directory structure in `/engineyard/portage/engineyard/`

```
mkdir /engineyard/portage/engineyard/app-admin/filebeat-bin
```

2) Download the files in https://gitweb.gentoo.org/repo/gentoo.git/tree/app-admin/filebeat-bin?id=686f3ae488f745ea2fc831907de519c07ac363df

Download the plain version. Below is a crude way to download the files one at a time.

```
cd /engineyard/portage/engineyard/app-admin/filebeat-bin
wget https://gitweb.gentoo.org/repo/gentoo.git/plain/app-admin/filebeat-bin/filebeat-bin-1.0.1.ebuild?id=686f3ae488f745ea2fc831907de519c07ac363df
mv filebeat-bin-1.0.1.ebuild?id=686f3ae488f745ea2fc831907de519c07ac363df filebeat-bin-1.0.1.ebuild
wget https://gitweb.gentoo.org/repo/gentoo.git/plain/app-admin/filebeat-bin/metadata.xml?id=686f3ae488f745ea2fc831907de519c07ac363df
mv metadata.xml?id=686f3ae488f745ea2fc831907de519c07ac363df metadata.xml
mkdir files
cd files
wget https://gitweb.gentoo.org/repo/gentoo.git/plain/app-admin/filebeat-bin/files/filebeat.confd?id=686f3ae488f745ea2fc831907de519c07ac363df
mv filebeat.confd?id=686f3ae488f745ea2fc831907de519c07ac363df filebeat.confd
wget https://gitweb.gentoo.org/repo/gentoo.git/plain/app-admin/filebeat-bin/files/filebeat.initd?id=686f3ae488f745ea2fc831907de519c07ac363df
mv filebeat.initd?id=686f3ae488f745ea2fc831907de519c07ac363df filebeat.initd
```

3) Digest

```
ebuild filebeat-bin-1.0.1.ebuild digest
```

4) Unmask

```
echo "=app-admin/filebeat-bin-1.0.1 ~amd64" >> /etc/portage/package.keywords/local
```

5) Install

```
emerge =app-admin/filebeat-bin-1.0.1
```

6) Profit!
---

http://www.gentoo-wiki.info/HOWTO_Installing_3rd_Party_Ebuilds

Example: Install `app-admin/filebeat-bin` from Gentoo portage

1) Create the directory structure in `/engineyard/portage/engineyard/`

```
mkdir /engineyard/portage/engineyard/app-admin/filebeat-bin
```

2) Clone the repo and copy the package to the portage tree

```
git clone https://anongit.gentoo.org/git/repo/gentoo.git
cd gentoo/app-admin/
cp -rfv filebeat-bin /engineyard/portage/app-admin
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

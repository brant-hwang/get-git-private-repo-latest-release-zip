### Github Latest Release Downloading Script (Private Repository)

```
ID={YOUR_GITHUB_ID}
PW={YOUR_GITHUB_PASSWORD}
OWNER={OWNER}
REPO={REPOSITORY}

curl -u $ID:$PW https://api.github.com/repos/$OWNER/$REPO/releases/latest > latest.json
TAG_NAME=`cat latest.json | jq '.tag_name' |  tr -d '"'`
URL="https://github.com/$OWNER/$REPO/archive/$TAG_NAME.zip"
curl -O -J -L -u $ID:$PW $URL
```

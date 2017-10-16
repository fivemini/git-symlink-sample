# git-symlink-sample

$ git log --oneline


bd9baa0 mkdir server && cd server && ln -s ../common common
f0f3490 echo 'util' > common/util.txt
10e5601 Initial commit


$ git cat-file -p bd9baa0


tree 2d5888f81032e952a6772adaf57029f16de8cf7c
parent f0f34902c81c88f2eeb54964b5dce394b86c0054
author fivemini <> 1508153622 +0900
committer fivemini <> 1508153622 +0900

mkdir server && cd server && ln -s ../common common


$ git cat-file -p 2d5888f


100644 blob 050c291240893dc13be3299c6ae056f573cb5ce0    README.md
040000 tree 85fc703c91585c0f468a55ea33e2cea69f818a44    common
040000 tree 6599fe6026f3bcb13f43078e397469a44f8b994d    server


$ git cat-file -p 6599fe6


120000 blob 60d3b0a6a8f6b087f0bb4cfbffe75e2ebb4793d2    common


$ git cat-file -p 60d3b0a


../common


$ git log --oneline


5c1027d echo 'updated util' >> common/util.txt
bd9baa0 mkdir server && cd server && ln -s ../common common
f0f3490 echo 'util' > common/util.txt
10e5601 Initial commit


$ git cat-file -p 5c1027d


tree 5f03d6b96d3d7ebff4fb13b3bddfa7ece32f366b
parent bd9baa00078b6118bb08e73903ef6963b7cd1da9
author fivemini <> 1508155934 +0900
committer fivemini <> 1508155934 +0900

echo 'updated util' >> common/util.txt


$ git cat-file -p 5f03d6b


100644 blob 050c291240893dc13be3299c6ae056f573cb5ce0    README.md
040000 tree 4deef70f113a5a6c65e8e2d2485a05e6af312ac5    common
040000 tree 6599fe6026f3bcb13f43078e397469a44f8b994d    server


$ cat server/common/util.txt
util
updated util


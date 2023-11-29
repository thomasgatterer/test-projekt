https://inf-schule.de/software/verteilte_versions_verwaltung_git/lokale_repositories/einchecken_mit_add_und_commit


  ausgabe-status() {
  echo "HEAD:               $(git cat-file -p HEAD:test-datei.txt)"
  echo "Index:              $(git cat-file -p :test-datei.txt)"
  echo "Arbeitsverzeichnis: $(cat test-datei.txt)"
  }


Einchecken mit add und commit
-----------------------------

echo "Version 2" > test-datei.txt
git add test-datei.txt
git commit -m "v2 eingecheckt"
echo "Version 3" > test-datei.txt
git commit test-datei.txt -m "v3 eingecheckt"

------------------------------------------


Auschecken mit reset und checkout
---------------------------------

echo "Version 4" > test-datei.txt
git add test-datei.txt 
echo "Version 5" > test-datei.txt 

PAUSE
ausgabe-status

git reset -- test-datei.txt

ausgabe-status

git checkout -- test-datei.txt

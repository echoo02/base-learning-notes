git clone https://github.com/YOUR_USERNAME/base-learning-notes.git
cd base-learning-notes
touch README.md notes.md base.md resources.md progress.md
git add .
git commit -m "initial repository setup"
#!/bin/bash

FILES=("README.md" "notes.md" "base.md" "resources.md" "progress.md")

MESSAGES=(
"update notes"
"improve documentation"
"add base notes"
"minor edits"
"cleanup formatting"
"expand section"
"update progress"
"clarify explanation"
"improve readability"
"add references"
)

for i in {1..50}
do
  FILE=${FILES[$RANDOM % ${#FILES[@]}]}
  MESSAGE=${MESSAGES[$RANDOM % ${#MESSAGES[@]}]}

  echo "- update $i on $(date)" >> $FILE

  git add $FILE
  git commit -m "$MESSAGE"

  # sleep between commits (change 300–3600 for slower pace)
  sleep $((RANDOM % 300 + 60))
done
chmod +x commits.sh
./commits.sh
git push


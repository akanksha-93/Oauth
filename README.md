# To push new project to Git repository
echo "# Oauth" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/akanksha-93/Oauth.git
git push -u origin main
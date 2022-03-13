```bash
sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

gem install jekyll bundler

#navigate to directory 
bundle install

bundle exec jekyll serve

## npm run == to get into bash
docker run -it --rm --name blog-node --volume="$PWD:/srv/jekyll" node:10-slim bash

npm install
npm install -g gulp
```

### Docker
```bash
#incase of fedora, rhel, centos
chcon -Rt svirt_sandbox_file_t .

#docker build
docker run --rm -it --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" --env JEKYLL_ENV=production jekyll/jekyll jekyll build

#docker run
docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" --env JEKYLL_ENV=development -p 4000:4000 jekyll/jekyll jekyll serve

```
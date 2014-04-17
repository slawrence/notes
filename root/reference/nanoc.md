Nanoc Notes
============

### Setup

adsf is required for `nanoc view` and kramdown is for markdown

    git clone http://github.com/slawrence/blog.git
    cd blog
    gem install nanoc
    gem install adsf
    gem install kramdown


### Basic workflow

1. `rake new_post['Title_of_Post']`
2. Make edits
3. `nanoc compile`
4. `nanoc view`
5. `rake deploy:rsync`

### Deploy Setup (Rsync)

1. Add deploy hash to `config.yaml`

        deploy:
            public:
                kind: rsync
                dst:  "username@website.com:~/public_html"

2. Execute `nanoc deploy`

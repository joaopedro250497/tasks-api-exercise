#  Creating an API for tasks and stories

API created using rails to generate, edit and delete stories, tasks and statuses. Pagination and filtering are done by pagy and ramsack.

## System Versions
- **Ruby**: 3.4.1
- **Rails**: 7.2.2.1

---

## To install Ruby, it is necessary to configure asdf  
- **Environment used: Ubuntu** 24.04 LTS  

### 1. Installing asdf  
Run the following commands in the terminal:  

```bash
# Clone asdf
git clone https://github.com/asdf-vm/asdf.git ~/.asdf

# Configure asdf in the shell (Bash or Zsh)
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc

# For Zsh:
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc

# Update the shell
source ~/.zshrc 
# or 
source ~/.bashrc
```

### 2. Install the Ruby plugin  
Add the Ruby plugin to asdf:  

```bash
asdf plugin add ruby https://github.com/asdf-vm/asdf-ruby.git
```

### 3. Install dependencies to compile Ruby  
On Linux (Debian/Ubuntu), install:  

```bash
sudo apt install -y autoconf bison build-essential libssl-dev libyaml-dev \
libreadline-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm-dev libpq-dev
```

### 4. Install a Ruby version  
List the available versions and install the desired one:  

```bash
# List versions
asdf list-all ruby

# Install a version (example: 3.3.5 project version)
asdf install ruby 3.3.5

# Set as global
asdf global ruby 3.3.5
```
Check if Ruby was installed correctly:  
```bash
ruby -v
# then, inside the project folder, run bundler.

bundler install
```

## How to Initiate the Project

First, you will have to create an user for PostgreSQL:

```bash
# open Postgresql Console:
sudo -u postgres psql

# alter postgres password:
ALTER USER postgres PASSWORD 'postgres';

# create a role username:
CREATE ROLE username WITH LOGIN PASSWORD 'postgres';

# set username as a superuser:
ALTER ROLE username WITH SUPERUSER;

# exit Console:
\q
```

Create the database and run the migrations:

```bash
rails db:create
rails db:migrate
```
Run the application with:

```bash
rails server
```

### Now you can send requisitions using [Bruno](https://www.usebruno.com/).
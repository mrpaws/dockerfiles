from ubuntu:14.04
maintainer mrpaws "<paws@delimitize.com>" 

run useradd -d /home/paws -s /usr/bin/zsh -mc "paws" paws
run apt-get update && apt-get install -y zsh tmux screen cowsay fortune unzip wget openssh-server && \
  mkdir -p /home/paws/.ssh && echo "/usr/games/fortune  | /usr/games/cowsay" >> /etc/zsh/zprofile 

add ./authorized_keys /home/paws/.ssh/
add ./sshd_config /etc/ssh/
add ./zshrc /home/paws/.zshrc 
add ./gitconfig /home/paws/.gitconfig

run chown -R paws:paws /home/paws && chmod 750 /home/paws 
run mkdir -p /var/run/sshd

expose 22

cmd ["/usr/sbin/sshd", "-D"]

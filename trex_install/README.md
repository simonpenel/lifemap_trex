#INSTALLATION DE TREX
sudo apt-get update
sudo apt install build-essential
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
sudo apt install pkg-config
sudo apt-get install gdal-bin 
sudo apt-get install libgdal-dev
sudo apt-get install libssl-dev

git clone https://github.com/t-rex-tileserver/t-rex.git
cd t-rex
cargo build
cargo build --release

#CONFIGURATION
Copier le contenu du repertoire trex_install/html dans trex_install/t-rex/html
Au besoin modifier les ip dans les fichies json
  "http://134.214.213.37/ranks/{z}/{x}/{y}.pbf"

#LANCEMENT
Dans trex_install/t-rex

./target/release/t_rex serve --config=../../config_lifemap

# INSTALL AND LAUNCH_TREX

## Install t_rex

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

## Configuration

Copy the contents of  directory `trex_install/html` into  `trex_install/t-rex/html`

If needed, modify the I.P in json files (for example http://134.214.213.37/ranks/{z}/{x}/{y}.pbf )

## Launch t-rex

        cd trex_install/t-rex
        ./target/release/t_rex serve --config=../../config_lifemap

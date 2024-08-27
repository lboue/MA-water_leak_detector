# MA-water_leak_detector

## ZAP file

**ZAP Install**

    ./scripts/tools/zap/zap_download.py
    2024-08-27 13:22:39 root INFO    Found required zap version to be: v2024.08.14-nightly
    2024-08-27 13:22:39 root INFO    Fetching: https://github.com/project-chip/zap/releases/download/v2024.08.14-nightly/zap-linux-x64.zip
    2024-08-27 13:22:45 root INFO    Data downloaded, extracting ...
    2024-08-27 13:22:48 root INFO    Done extracting.
    export ZAP_INSTALL_PATH=/home/ludovic/connectedhomeip/.zap/zap-v2024.08.14-nightly    

**ZAP change device type dans clusters**

    /scripts/tools/zap/run_zaptool.sh /home/ludovic/connectedhomeip/examples/chef/devices/template.zap

**ZAP rename**

    ./examples/chef/sample_app_util/sample_app_util.py zap --rename-file examples/chef/devices/rootnode_waterleakdetector.zap
    Renamed from: examples/chef/devices/rootnode_waterleakdetector.zap to examples/chef/devices/rootnode_waterleakdetector_0b067acfa3.zap

**Generate Matter file**

    ./scripts/tools/zap/generate.py examples/chef/devices/rootnode_waterleakdetector_0b067acfa3.zap


## Build

    ./examples/chef/chef.py -t linux -d rootnode_waterleakdetector_0b067acfa3 -b

## Run example

    ./examples/chef/linux/out/rootnode_waterleakdetector_0b067acfa3

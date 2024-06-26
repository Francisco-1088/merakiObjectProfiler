# merakiNetworkObjectProfiler
Creates and Updates Meraki Dashboard Network Policy Objects

## How to Use

1. Clone repo to your working directory with `git clone https://github.com/Francisco-1088/merakiNetworkObjectProfiler.git`
2. Edit `config.py`
* Add your API Key under `api_key` in line 2
* Add your Organization ID under `org_id` in line 3. This will be the Organization ID for the target organization where the objects will be configured, and it can be obtained by scrolling all the way down in your Meraki Dashboard and making note of the organization ID value at the bottom.
3. Run `pip install -r requirements.txt` to install required libraries
4. Edit the sample `objects_sample.csv` file with the actual objects you're looking to provision and rename it to just `objects.csv`. At this point, the group column does nothing but in the future it will also provision groups and associate objects with groups.
5. After this, run the `main.py` file by executing `python main.py`. This will proceed to configure all ports in your network according to the CSV file provided.


## Caveats

1. For CIDR and Host objects, only IPv4 objects are supported
2. This will verify existing objects in your organization by name, and if there are matches in your CSV file, the script will update these objects to the values specified in your CSV

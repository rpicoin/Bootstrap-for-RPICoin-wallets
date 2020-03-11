# Linearize
Construct a linear, no-fork, best version of the RPICoin blockchain. The scripts
run using Python 3 but are compatible with Python 2.

## Step 1: Download hash list

    $ ./linearize-hashes.py linearize.cfg > hashlist.txt

Required configuration file settings for linearize-hashes:
* RPC: `datadir` (Required if `rpcuser` and `rpcpassword` are not specified)
* RPC: `rpcuser`, `rpcpassword` (Required if `datadir` is not specified)

Optional config file setting for linearize-hashes:
* RPC: `host`  (Default: `127.0.0.1`)
* RPC: `port`  (Default: `18000`)
* Blockchain: `min_height`, `max_height`
* `rev_hash_bytes`: If true, the written block hash list will be
byte-reversed. (In other words, the hash returned by getblockhash will have its
bytes reversed.) False by default. Intended for generation of
standalone hash lists but safe to use with linearize-data.py, which will output
the same data no matter which byte format is chosen.

The `linearize-hashes` script requires a connection, local or remote, to a
JSON-RPC server. Running `rpicoind` or `rpicoin-qt -server` will be sufficient.

## Step 2: Copy local block data

    $ ./linearize-data.py linearize.cfg

Required configuration file settings:
* `output_file`: The file that will contain the final blockchain.
      or
* `output`: Output directory for linearized `blocks/blkNNNNN.dat` output.

Optional config file setting for linearize-data:
* `debug_output`: Some printouts may not always be desired. If true, such output
will be printed.
* `file_timestamp`: Set each file's last-accessed and last-modified times,
respectively, to the current time and to the timestamp of the most recent block
written to the script's blockchain.
* `genesis`: The hash of the genesis block in the blockchain.
* `input`: rpicoind blocks/ directory containing blkNNNNN.dat
* `hashlist`: text file containing list of block hashes created by
linearize-hashes.py.
* `max_out_sz`: Maximum size for files created by the `output_file` option.
(Default: `1000*1000*1000 bytes`)
* `netmagic`: Network magic number.
* `out_of_order_cache_sz`: If out-of-order blocks are being read, the block can
be written to a cache so that the blockchain doesn't have to be sought again.
This option specifies the cache size. (Default: `100*1000*1000 bytes`)
* `rev_hash_bytes`: If true, the block hash list written by linearize-hashes.py
will be byte-reversed when read by linearize-data.py. See the linearize-hashes
entry for more information.
* `split_timestamp`: Split blockchain files when a new month is first seen, in
addition to reaching a maximum file size (`max_out_sz`).


# Automated the process to always have a recent bootstrap.bin available for download
		Bootstrap will run via a cronjob on a weekly basis

> Please see bootstrap_generator.sh



# RPICoin Bootstrap resources & information for end- uusers

## Instructions for the RPICoin USERS - but please use this method only if you are stuck while trying to sync your wallet. 

* Please always backup your wallet.dat and private key before making any changes.
* Turn off the wallet and download our bootstrap file https://rpicoin.com/bootstrap.dat 
* Move the bootstrap.dat you just downloaded to the %appdata%/Roaming/RPICOIN folder.

**Recommended to have a higher success ratio! (just do it):**
 Delete all the files **EXCEPT your wallet.dat** in the RPICOIN data directory, make sure you now only have the **wallet.dat** and the just moved **bootstrap.dat** files in there - or a clean update/installation. Or just create a new folder and copy all the RPICOIN folder content to it, in case you need the files again.


#### Locations of the RPICOIN data directory for each operating system:

**Linux =**
		~/.rpicoin/
**or**
		/root/.rpicoin/ **or** /home/<yourlinuxusername>/.rpicoin

**MacOS =** 
		$HOME/Library/Application Support/rpicoin/
**or**
		/Users/username/Library/Application Support/rpicoin/

**Windows:**
		%APPDATA%/Rpicoin
**or**
		C:\Users\<yourusername>\AppData\Roaming\Rpicoin

* **Start your wallet again**
It should start indexing/updating the blocks shortly after, after it finishes the syncing process, the bootstrap.dat file will be automatically renamed to bootstrap.dat.old. You can safely delete the file if you wish.

Note: If your wallet stays hidden during the process, or appears to have frozen, just give it enough time (or check if the blk000*.dat files in the data directory are increasing in size).
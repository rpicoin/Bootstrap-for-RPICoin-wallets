// Configuration details to connect to a RPICoin daemon
// This method uses the RPC functions of RPICoins daemon
// these settings are stored in ~/.rpicoin/rpicoin.conf ^^


# rpicoin RPC settings (linearize-hashes)
rpcuser=rpcusr
rpcpassword=rpcpassword
#datadir=~/.rpicoin
host=127.0.0.1

#mainnet default
port=18000

# bootstrap.dat hashlist settings (linearize-hashes)
# at this moment, the height is approx. **
# 510*(510*10)+1
max_height=2601001

# bootstrap.dat input/output settings (linearize-data)

# mainnet
netmagic=9feb4b9d
genesis=7d5eaec2dbb75f99feadfa524c78b7cabc1d8c8204f79d4f3a83381b811b0adc
# path should be an absolute path
# input=/home/example/.rpicoin/blocks
input=/home/{USERNAME}/.rpicoin/blocks

# testnet
#netmagic=
#genesis=
#input=/home/example/.rpicoin/testnet5/blocks

# "output" option causes blockchain files to be written to the given location,
# with "output_file" ignored. If not used, "output_file" is used instead.
# output=/home/example/blockchain_directory
# path should be an absolute path
# output_file=/home/example/Downloads/bootstrap.dat
output_file=/home/{USERNAME}/Desktop/bootstrap.dat
hashlist=hashlist.txt

# Maximum size in bytes of out-of-order blocks cache in memory
out_of_order_cache_sz = 100000000

# Do we want the reverse the hash bytes coming from getblockhash?
rev_hash_bytes = False

# On a new month, do we want to set the access and modify times of the new
# blockchain file?
file_timestamp = 0
# Do we want to split the blockchain files given a new month or specific height?
split_timestamp = 0

# Do we want debug printouts?
debug_output = False

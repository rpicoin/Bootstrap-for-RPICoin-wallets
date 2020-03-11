# bitcoind RPC settings (linearize-hashes)
rpcuser=someuser
rpcpassword=somepassword
#datadir=~/.rpicoin
host=127.0.0.1

#mainnet default
port=18000

#testnet default
#port=18002

#regtest default
#port=18004

# bootstrap.dat hashlist settings (linearize-hashes)
max_height=350000

# bootstrap.dat input/output settings (linearize-data)

# mainnet
netmagic=20451277
genesis=0000ec93e0a3fe0aafa3be7dafe1290f5fca039a4037dd5174bc3dd7a35d67f0
input=/home/example/.rpicoin/blocks

# testnet
#netmagic=21461378
#genesis=03205c57ebefb02d86c2c0c2de368fa48e92f7df7240f1b528ebbeae70fdbdb1
#input=/home/example/.rpicoin/testnet4/blocks

# "output" option causes blockchain files to be written to the given location,
# with "output_file" ignored. If not used, "output_file" is used instead.
# output=/home/example/blockchain_directory
output_file=/home/example/Downloads/bootstrap.dat
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
# kasm

--Swap file

sudo dd if=/dev/zero bs=1M count=1024 of=/mnt/1GiB.swap

sudo chmod 600 /mnt/1GiB.swap

sudo mkswap /mnt/1GiB.swap

sudo swapon /mnt/1GiB.swap
;;;

--Verify swap exists

cat /proc/swaps


--Add swap to fstab

echo '/mnt/1GiB.swap swap swap defaults 0 0' | sudo tee -a /etc/fstab
;;;


--Download the KASM set up

wget https://kasm-static-content.s3.amazonaws.com/kasm_release_1.10.0.238225.tar.gz
;;;

--Unzip the set up files.

tar -xf kasm_release*.tar.gz
;;;

--Start the set up script.

sudo bash kasm_release/install.sh

/-/-/-/--------------------------------------------------

curl "https://binaries.twingate.com/connector/setup.sh" | sudo TWINGATE_ACCESS_TOKEN="eyJhbGciOiJFUzI1NiIsImtpZCI6IjZkMExpQkVjVGYzT0UwRkRWWlhJNUljaXhzc1ptNV9sREFsdGRfU0F0RHMiLCJ0eXAiOiJEQVQifQ.eyJudCI6IkFOIiwiYWlkIjoiMTE2OTU2IiwiZGlkIjoiODA0NTI3IiwianRpIjoiMzQ1NDJjZjItNWM4YS00YTU2LTlkNGQtZDI5ZmQ0NTgwYmRjIiwiaXNzIjoidHdpbmdhdGUiLCJhdWQiOiJjeWJlcm9wcyIsImV4cCI6MTY4OTQ0MzUwMiwiaWF0IjoxNjg5NDM5OTAyLCJ2ZXIiOiI0IiwidGlkIjoiNDIyODkiLCJybnciOjE2ODk0NDAyMDIsInJuZXRpZCI6IjUyMjc4In0.TYMqKrr_krYbaR6XfZosOEkVRSynVWnKNn9ZEIbBSYdF8idSwyAmY4ZKH_cffgdHPjKw-RoWIZX6eBhsVBQinQ" TWINGATE_REFRESH_TOKEN="QryIBJTRdnKKaKnSFtvMaAvSiTqMDQgr13jSZN0QbcBvIl83nfv86ktb53JPuPVvSFI05x6aGqzktU9g-BPmYACpsr-4oZAvPnQXwl7lr49lR2486AcFxYQEhTwLcw0nYtEvEw" TWINGATE_NETWORK="cyberops" bash

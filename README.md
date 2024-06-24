# TM
import requests

user_input = str(input("Hash or txid?"))
response = requests.get("https://api.blockcypher.com/v1/btc/main/txs/"+user_input)

print(response) 
if response.status_code != 200:
 print("error")
else:
 print("Inputs: ",response.json()['inputs'])
 print("Outputs", response.json()['outputs'])
 print("Addresses", response.json()['addresses'])

## Create Google DNS Managed Zone

Buy domain name from domain name service i.e. namecheap.com. Create DNS zone named `federation` pointing to the domain that you buy.
```
gcloud dns managed-zones create federation \
  --description "Kubernetes federation testing" \
  --dns-name giri.foo
```
Google will ask to verify, put TXT record in namecheap with the code that Google ask. Now the DNS managed zone should be ready.

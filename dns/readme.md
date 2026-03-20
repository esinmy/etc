# CMD. The domain should end with a trailing dot so the resolver does not apply the search list or append the home domain.
# Using a trailing dot makes the domain a fully qualified domain name, so it is resolved exactly as written
nslookup -q=TXT <domain>. 8.8.8.8

# PowerShell.
Resolve-DnsName <domain> -Type TXT -Server 8.8.8.8

# dig
dig @8.8.8.8 <domain> TXT



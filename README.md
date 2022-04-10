<p align="center">
  <img alt="Metabigor" src="https://user-images.githubusercontent.com/23289085/143042137-28f8e7e5-e485-4dc8-a09b-10759a593210.png" height="140" />
  <p align="center">Intelligence Tool but without API key</p>
  <p align="center">
    <a href="https://github.com/j3ssie/metabigor"><img alt="Release" src="https://img.shields.io/github/v/release/j3ssie/metabigor.svg"></a>
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
  </p>
</p>

## What is Metabigor?

Metabigor is Intelligence tool, its goal is to do OSINT tasks and more but without any API key.

## Installation

```
GO111MODULE=on go install github.com/j3ssie/metabigor@latest
```

## Main features

- Searching information about IP Address, ASN and Organization.
- Wrapper for running rustscan, masscan and nmap on IP/CIDR.
- Finding more root domains by searching certificate information on crt.sh
- Get Summary about IP address (powered by [@thebl4ckturtle](https://github.com/theblackturtle))
- Do searching from the command line on some search engine.


## Example Commands

```
Examples Commands:
# discovery IP of a company/organization
echo "company" | metabigor net --org -o /tmp/result.txt

# discovery IP of an ASN
echo "ASN1111" | metabigor net --asn -o /tmp/result.txt
cat list_of_ASNs | metabigor net --asn -o /tmp/result.txt

# Only run masscan full ports
echo '1.2.3.4/24' | metabigor scan -o result.txt

# only run nmap detail scan based on pre-scan data
echo '1.2.3.4:21' | metabigor scan -s -c 10
echo '1.2.3.4:21' | metabigor scan --tmp /tmp/raw-result/ -s -o result.txt
echo '1.2.3.4 -> [80,443,2222]' | metabigor scan -R

# only run scan with zmap
cat ranges.txt | metabigor scan -p '443,80' -z

# certificate search info on crt.sh
echo 'Target' | metabigor cert

# find more root domains
echo 'Target Inc' | metabigor cert --json | jq -r '.Domain' | unfurl format %r.%t | sort -u

# Get Summary about IP address (powered by @thebl4ckturtle)
cat list_of_ips.txt | metabigor ipc --json
```

## Demo

[![asciicast](https://asciinema.org/a/301745.svg)](https://asciinema.org/a/301745)

## Credits

Logo from [flaticon](https://image.flaticon.com/icons/svg/1789/1789851.svg)
by [freepik](https://www.flaticon.com/authors/freepik)

## Disclaimer

This tool is for educational purposes only. You are responsible for your own actions. If you mess something up or break
any laws while using this software, it's your fault, and your fault only.

## License

`Metabigor` is made with ♥ by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.

## Donation

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://paypal.me/j3ssiejjj)

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/j3ssie)

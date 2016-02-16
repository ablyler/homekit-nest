# homekit-nest
HomeKit Support for [Nest](http://nest.com) using [HomeControl](https://github.com/brutella/hc) and ~~[lifx](https://github.com/wolfeidau/lifx)~~ [Nest go library]https://github.com/jsgoecke/nest).

Nest thermostats are automatically discovered and published as HomeKit accessories on your local network.
After pairing the thermostats with HomeKit using any iOS HomeKit app (e.g. [Home](http://selfcoded.com/home/)), you can:

- use Siri to control your thermostats voice command – *Hey Siri set temprature to 70 degrees*
- remotely access your lights using HomeKit Remote Access (HomeKit uses strong end-to-end encryption)

# Getting Started

1. [Install Go](http://golang.org/doc/install)
2. [Setup Go workspace](http://golang.org/doc/code.html#Organization)
3. Install

        cd $GOPATH/src
        
        # Clone project
        git clone https://github.com/ablyler/homekit-nest.git && cd homekit-nest
        
        # Install dependencies
        go get

4. Register new app w/ [Nest Developer Portal](https://developer.nest.com)

5. Run

        go run hknest.go -nest-pin "XXXXXX" -homekit-pin "00102003" -product-id "XXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXX" -product-secret "XXXXXXXXXXXX" -state foo -v

**Command Line Arguments**

Required

- `-homekit-pin [8-digits]` must be entered on iOS to pair with the light bulb(s)
- `-nest-pin` authorization code from Nest - https://developer.nest.com/documentation/how-to-auth
- `-product-id` id of the product that you registered on the Nest developer portal
- `-product-secret` secret key of the product that you registered on the Nest developer portal
- `-state` a value you create, used during OAuth

Optional

- `-v` for verbose log output

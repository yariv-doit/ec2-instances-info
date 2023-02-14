# ec2-instances-info

![Build Status](https://github.com/LeanerCloud/ec2-instances-info/workflows/Test/badge.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/LeanerCloud/ec2-instances-info)](https://goreportcard.com/report/github.com/LeanerCloud/ec2-instances-info)
[![GoDoc](https://godoc.org/github.com/LeanerCloud/ec2-instances-info?status.svg)](http://godoc.org/github.com/LeanerCloud/ec2-instances-info)

Golang library providing specs and pricing information about AWS EC2 instances,
based on the data that is also powering the comprehensive
[www.ec2instances.info](http://www.ec2instances.info) instance comparison
website.

## History

This used to be a part of my other project
[AutoSpotting](https://github.com/LeanerCloud/autospotting) which uses it
intensively, but I decided to extract it into a dedicated project since it may be
useful to someone else out there.

Some data fields that were not needed in AutoSpotting may not yet be exposed but
they can be added upon demand.

## Installation or update

You will need Go 1.16 or latest, then it's a matter of installing it as usual using `go get`

```text
go get -u github.com/LeanerCloud/ec2-instances-info/...
```

## Usage

```golang
import "github.com/LeanerCloud/ec2-instances-info"

data, err := ec2instancesinfo.Data() // only needed once

// This would print all the available instance type names:
for _, i := range *data {
  fmt.Println("Instance type", i.InstanceType)
}
```

See the examples directory for a working code example.

## Contributing

Pull requests and feedback are welcome.

The data can be updated for new instance type coverage by running `make`.

## Try it out on GCP Cloud Shell

- [![Open in Cloud Shell](http://gstatic.com/cloudssh/images/open-btn.svg)](https://ssh.cloud.google.com/cloudshell/editor?cloudshell_git_repo=https://github.com/LeanerCloud/ec2-instances-info.git)

- Click on the `Terminal` then `New Terminal` in the top menu
- In the terminal run `cd ~/cloudshell_open/ec2-instances-info/examples/instances/`
- `go run .` will run the example code.

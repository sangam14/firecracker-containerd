# Copyright 2018-2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License"). You may
# not use this file except in compliance with the License. A copy of the
# License is located at
#
# 	http://aws.amazon.com/apache2.0/
#
# or in the "license" file accompanying this file. This file is distributed
# on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either
# express or implied. See the License for the specific language governing
# permissions and limitations under the License.

all: runtime

runtime: containerd-shim-aws-firecracker

containerd-shim-aws-firecracker: *.go
	go build -o containerd-shim-aws-firecracker

install: containerd-shim-aws-firecracker
	install -D -o root -g root -m755 -t $(INSTALLROOT)/bin containerd-shim-aws-firecracker

clean:
	- rm -f containerd-shim-aws-firecracker

.PHONY: all runtime clean install

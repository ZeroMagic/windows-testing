# Copyright 2019 The Kubernetes Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

ARG BASE_IMAGE=microsoft/windowsservercore:1803
FROM $BASE_IMAGE

ADD https://github.com/etcd-io/etcd/releases/download/v3.3.10/etcd-v3.3.10-windows-amd64.zip /
RUN powershell -Command "Expand-Archive -Path C:\etcd-v3.3.10-windows-amd64.zip -DestinationPath C:\usr\local -Force ;\
Rename-Item -Path C:\usr\local\etcd-v3.3.10-windows-amd64 -NewName C:\usr\local\bin" &&\
del C:\etcd-v3.3.10-windows-amd64.zip
ENTRYPOINT ["/usr/local/bin/etcd.exe"]

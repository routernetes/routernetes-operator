# API Reference

Packages:

- [routernetes.net/v1alpha1](#routernetesnetv1alpha1)

# routernetes.net/v1alpha1

Resource Types:

- [Router](#router)




## Router
<sup><sup>[↩ Parent](#routernetesnetv1alpha1 )</sup></sup>






Router is the Schema for the routers API

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
      <td><b>apiVersion</b></td>
      <td>string</td>
      <td>routernetes.net/v1alpha1</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b>kind</b></td>
      <td>string</td>
      <td>Router</td>
      <td>true</td>
      </tr>
      <tr>
      <td><b><a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#objectmeta-v1-meta">metadata</a></b></td>
      <td>object</td>
      <td>Refer to the Kubernetes API documentation for the fields of the `metadata` field.</td>
      <td>true</td>
      </tr><tr>
        <td><b><a href="#routerspec">spec</a></b></td>
        <td>object</td>
        <td>
          Spec defines the desired state of Router<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>status</b></td>
        <td>object</td>
        <td>
          Status defines the observed state of Router<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec
<sup><sup>[↩ Parent](#router)</sup></sup>



Spec defines the desired state of Router

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#routerspecinterfaces">interfaces</a></b></td>
        <td>object</td>
        <td>
          Configuration for host interfaces<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b><a href="#routerspecdhcp">dhcp</a></b></td>
        <td>object</td>
        <td>
          Defines the configuration for the DHCP server<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#routerspecdns">dns</a></b></td>
        <td>object</td>
        <td>
          Defines the configuration for the DNS server<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#routerspecfirewall">firewall</a></b></td>
        <td>object</td>
        <td>
          Firewall zone settings<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b><a href="#routerspecosupdates">osUpdates</a></b></td>
        <td>object</td>
        <td>
          Configuration for CoreOS auto-updates<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.interfaces
<sup><sup>[↩ Parent](#routerspec)</sup></sup>



Configuration for host interfaces

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#routerspecinterfacesinsideindex">inside</a></b></td>
        <td>[]object</td>
        <td>
          Inside (internal) interfaces<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b><a href="#routerspecinterfacesoutsideindex">outside</a></b></td>
        <td>[]object</td>
        <td>
          Outside (external) interfaces<br/>
        </td>
        <td>true</td>
      </tr></tbody>
</table>


### Router.spec.interfaces.inside[index]
<sup><sup>[↩ Parent](#routerspecinterfaces)</sup></sup>



An inside interface

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#routerspecinterfacesinsideindexipv4">ipv4</a></b></td>
        <td>object</td>
        <td>
          IPv4 address settings<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>
          Interface name<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>type</b></td>
        <td>string</td>
        <td>
          Interface type (for instance, ethernet)<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>members</b></td>
        <td>[]string</td>
        <td>
          List of bridge members, only required when interface type is bridge<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.interfaces.inside[index].ipv4
<sup><sup>[↩ Parent](#routerspecinterfacesinsideindex)</sup></sup>



IPv4 address settings

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>method</b></td>
        <td>string</td>
        <td>
          auto or manual<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>address</b></td>
        <td>string</td>
        <td>
          Static address, for example 192.168.1.1/24. Only required when method is manual<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.interfaces.outside[index]
<sup><sup>[↩ Parent](#routerspecinterfaces)</sup></sup>



An outside interface

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#routerspecinterfacesoutsideindexipv4">ipv4</a></b></td>
        <td>object</td>
        <td>
          IPv4 address settings<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>name</b></td>
        <td>string</td>
        <td>
          Interface name<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>type</b></td>
        <td>string</td>
        <td>
          Interface type (for instance, ethernet)<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>members</b></td>
        <td>[]string</td>
        <td>
          List of bridge members, only required when interface type is bridge<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.interfaces.outside[index].ipv4
<sup><sup>[↩ Parent](#routerspecinterfacesoutsideindex)</sup></sup>



IPv4 address settings

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>method</b></td>
        <td>string</td>
        <td>
          auto or manual<br/>
        </td>
        <td>true</td>
      </tr><tr>
        <td><b>address</b></td>
        <td>string</td>
        <td>
          Static address, for example 192.168.1.1/24. Only required when method is manual<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.dhcp
<sup><sup>[↩ Parent](#routerspec)</sup></sup>



Defines the configuration for the DHCP server

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>dnsServer</b></td>
        <td>string</td>
        <td>
          DNS server for the DHCP scope. Defaults to 192.168.64.1<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>domain</b></td>
        <td>string</td>
        <td>
          Domain for the DHCP scope. Defaults to network.lan<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>endIP</b></td>
        <td>string</td>
        <td>
          End IP for the DHCP scope. Defaults to 192.168.64.150<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>gateway</b></td>
        <td>string</td>
        <td>
          Gateway for the DHCP scope. Defaults to 192.168.64.1<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>leaseTime</b></td>
        <td>string</td>
        <td>
          DHCP lease time. Defaults to 12h<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>mask</b></td>
        <td>string</td>
        <td>
          Subnet mask for the DHCP scope. Defaults to 255.255.255.0<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>startIP</b></td>
        <td>string</td>
        <td>
          Start IP for the DHCP scope. Defaults to 192.168.64.50<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.dns
<sup><sup>[↩ Parent](#routerspec)</sup></sup>



Defines the configuration for the DNS server

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>listenInterface</b></td>
        <td>string</td>
        <td>
          Host interface that should be listening for DNS requests. Defaults to the first inside interface<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>upstreamServers</b></td>
        <td>[]string</td>
        <td>
          List of upstream DNS servers. Defaults to 8.8.8.8 and 8.8.4.4<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.firewall
<sup><sup>[↩ Parent](#routerspec)</sup></sup>



Firewall zone settings

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b><a href="#routerspecfirewalloutside">outside</a></b></td>
        <td>object</td>
        <td>
          Outside (external) firewall rules<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.firewall.outside
<sup><sup>[↩ Parent](#routerspecfirewall)</sup></sup>



Outside (external) firewall rules

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>services</b></td>
        <td>[]string</td>
        <td>
          List of permitted services<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>


### Router.spec.osUpdates
<sup><sup>[↩ Parent](#routerspec)</sup></sup>



Configuration for CoreOS auto-updates

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
    </thead>
    <tbody><tr>
        <td><b>day</b></td>
        <td>string</td>
        <td>
          Day of the week to check for updates, either in full or abbreviated (first three letters) form. Defaults to Sun<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>enabled</b></td>
        <td>boolean</td>
        <td>
          Whether to enable auto-updated. Defaults to true<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>time</b></td>
        <td>string</td>
        <td>
          Time to check for updates, in hh:mm ISO 8601 format. Defaults to 04:00<br/>
        </td>
        <td>false</td>
      </tr><tr>
        <td><b>timezone</b></td>
        <td>string</td>
        <td>
          Timezone for auto-updates. Defaults to UTC<br/>
        </td>
        <td>false</td>
      </tr></tbody>
</table>
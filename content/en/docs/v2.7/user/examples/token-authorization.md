---
type: docs
title: "Token Authorization"
linkTitle: "Token Authorization"
weight: 32
description: "Config token based authorization in dubbo"
---

Through the token authorization control center at the registry to decide whether to issue tokens to consumers, you can prevent consumers from bypassing the registry access provider, another through the registry can flexibly change the authorization without modification or upgrade provider


![/user-guide/images/dubbo-token.jpg](/imgs/user/dubbo-token.jpg)

You can turn on token authentication globally:

```xml
<!--Random token , generated using a UUID-->
<dubbo:provider token="true" />
```
or

```xml
<!--Fixed token, equivalent to the password-->
<dubbo:provider token="123456" />
```

Of course can turn on token authentication at service level:

```xml
<!--Random token , generated using a UUID-->
<dubbo:service interface="com.foo.BarService" token="true" />
```
or

```xml
<!--Fixed token, equivalent to the password-->
<dubbo:service interface="com.foo.BarService" token="123456" />
```

Also can turn on token authentication at protocol level:

```xml
<!--Random token , generated using a UUID-->
<dubbo:protocol name="dubbo" token="true" />
```
or

```xml
<!--Fixed token, equivalent to the password-->
<dubbo:protocol name="dubbo" token="123456" />
```

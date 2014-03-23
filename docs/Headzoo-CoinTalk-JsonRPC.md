Headzoo\CoinTalk\JsonRPC
===============

Used to query the coin rpc server.

Example:
<code>
 $conf = [
     "user" => "test",
     "pass" => "pass",
     "host" => "localhost",
     "port" => 9332
 ];
 $rpc  = new JsonRPC($conf);
 $info = $rpc->query("getinfo");
</code>


* Class name: JsonRPC
* Namespace: Headzoo\CoinTalk
* This class implements: [Headzoo\CoinTalk\JsonRPCInterface](Headzoo-CoinTalk-JsonRPCInterface.md)




Properties
----------


### $conf

```
private array $conf = array("user" => "test", "pass" => "test", "host" => "localhost", "port" => 9332)
```

Configuration for the litecoind rpc



* Visibility: **private**


### $http

```
private \Headzoo\CoinTalk\HTTPInterface $http
```

Used to make http request to the wallet



* Visibility: **private**


### $logger

```
private \Psr\Log\LoggerInterface $logger
```

Used to log messages



* Visibility: **private**


Methods
-------


### \Headzoo\CoinTalk\JsonRPC::__construct

```
mixed Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::__construct(array $conf, \Psr\Log\LoggerInterface $logger)
```

Constructor



* Visibility: **public**

#### Arguments

* $conf **array** - See the setConf() method
* $logger **Psr\Log\LoggerInterface** - Log requests and errors with this instance



### \Headzoo\CoinTalk\JsonRPC::setConf

```
\Headzoo\CoinTalk\JsonRPC Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::setConf(array $conf)
```

Sets the configuration for the rpc

The configuration array should contain 4 items:
 "user" - The rpc username, default "test"
 "pass" - The rpc password, default "test"
 "host" - The rpc server host, default "localhost"
 "port" - The rpc server port, default 9332

* Visibility: **public**

#### Arguments

* $conf **array** - Configuration for the rpc



### \Headzoo\CoinTalk\JsonRPC::setLogger

```
\Headzoo\CoinTalk\JsonRPC Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::setLogger(\Psr\Log\LoggerInterface $logger)
```

Sets a logger instance

Once set, requests and errors will be logged using the instance.

* Visibility: **public**

#### Arguments

* $logger **Psr\Log\LoggerInterface** - The logger



### \Headzoo\CoinTalk\JsonRPC::setHTTP

```
\Headzoo\CoinTalk\JsonRPC Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::setHTTP(\Headzoo\CoinTalk\HTTPInterface $http)
```

Sets the HTTPInterface used to make requests to the wallet



* Visibility: **public**

#### Arguments

* $http **[Headzoo\CoinTalk\HTTPInterface](Headzoo-CoinTalk-HTTPInterface.md)** - The HTTPInterface instance



### \Headzoo\CoinTalk\JsonRPC::getHTTP

```
\Headzoo\CoinTalk\HTTPInterface Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::getHTTP()
```

Returns the HTTPInterface instance used to make requests to the wallet

Automatically creates an instance if none has been set.

* Visibility: **public**



### \Headzoo\CoinTalk\JsonRPC::query

```
mixed Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::query($method, array $params)
```

Sends a raw query the litecoind rpc

Returns an array which contains the server response.

Example:
<code>
 $rpc  = new JsonRPC();
 $info = $rpc->query("getinfo");
 echo $info["version"];
 echo $info["balance"];
 echo $info["difficulty"];
</code>

* Visibility: **public**

#### Arguments

* $method **mixed**
* $params **array**



### \Headzoo\CoinTalk\JsonRPC::exec

```
string Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::exec(string $query)
```

Sends the query string to the server and returns the response



* Visibility: **protected**

#### Arguments

* $query **string** - The query string to send



### \Headzoo\CoinTalk\JsonRPC::log

```
null Headzoo\CoinTalk\JsonRPC::\Headzoo\CoinTalk\JsonRPC::log(mixed $level, string $message, array $context)
```

Logs a message with an arbitrary level when logging is enabled



* Visibility: **protected**

#### Arguments

* $level **mixed** - The logging level
* $message **string** - The message to log
* $context **array** - Values to place into the message



### \Headzoo\CoinTalk\JsonRPCInterface::query

```
array Headzoo\CoinTalk\JsonRPCInterface::\Headzoo\CoinTalk\JsonRPCInterface::query(string $method, array $params)
```

Sends a raw query the litecoind rpc

Returns an array which contains the server response.

Example:
<code>
 $rpc  = new JsonRPC();
 $info = $rpc->query("getinfo");
 echo $info["version"];
 echo $info["balance"];
 echo $info["difficulty"];
</code>

* Visibility: **public**
* This method is defined by [Headzoo\CoinTalk\JsonRPCInterface](Headzoo-CoinTalk-JsonRPCInterface.md)

#### Arguments

* $method **string** - The method to call
* $params **array** - The method parameters


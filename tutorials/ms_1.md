## Messaging Server Tutorial 1

### Introduction

With messaging server, one can build advanced applictions with complicated business logics and yet still maintain high performance.

### Creating a hello world service

First, we add the following to sitemap.xml:

{code}
    <services>
          <webSocket path="ws" xpipe="http://www.xmlpipe.org/xpe/ms/http" name="ms"/>
          
  <!-- We now redirect POST/GET requests to the above web socket using the sendTo attribute -->

        <service path="/hello"  sendTo="ms">
            <post  xpipe="http://www.xmlpipe.org/xpe/ms/http/request" />
            <get   xpipe="http://www.xmlpipe.org/xpe/ms/http/request" />
        </service>
                  
    </services>

{code}


Next, we edit the messaging model and save the following as hello.mml under src.ms:

{code}
<ms domain="hello">

  <topic  name='http' type='http' >
    <pub src='ws' protocol='http'  transport="ws" handler="hello" />      
  </topic>
    
    
    <handler name="hello" >
        <script src="hello.js" />
    </handler>
    
    
</ms>
{code}

We also add hello.js to src.ms:

{code}
/**
 * My module:
 *  description about what it does
 */
(function() {
    
    var process = function(req, resp) {
        resp.body="Hello world";
    };
    
    var getProcess = function(req, resp) {
        resp.body="Hello world: get";
    };
    
    
    return {
     onGet: getProcess,
     onPost: process
//     onPut:
//     onDel:
    };
    
}());
{code}


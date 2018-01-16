## Introduction
    
Before starting, we assume that you have good knowledge of HTML5, CSS, JavaScript, and basic knowledge of XML.  
    
It is important to point out that the application architecture of XPE is significantly different from the traditional architecture. The XPE architecture adopts the modern web architecture so all the UI logics are implemented in the browser ONLY powered by services on the server side. The communication between the UI and services is primarily JSON over HTTP for maximum data compatibility.  This architecture is shown below:
    
    
<img src="/images/primaryarch.png" alt="Primary architecture" width="600"/>
    
## Presentation Layer
    
<p>The presentation layer will implement all UI logics using standard HTML5/CSS/JavaScript.  It is important to only implement UI logics but not business logics. UI logics are those
        that help end users perform their tasks more easily.   
</p>
    
### Service Layer
    
<p>The service layer provides data services to the UI layer.  All services follow the <a href="/documentation/jrest">REST service style</a>.  With the XPE technologies, you can create new services with 
        simple configurations without coding.   
</p>
    
### Messaging Layer 
    
<p>The messaging layer hosts more complicated services which are implemented as reactors to events using Javascript.  This architecture allows a large number of events to 
        be processed efficiently and deterministically. 
</p>
    
### Classification of Web Applications 
    
<p>We classify web applications into the following levels:</p>
    
<table class="table table-striped">
        <tr>
            <th>Level</th>
            <th>Description</th>
            <th>Example</th>
            <th>Notes</th>
        </tr>
        <tr>
            <td>Level 0</td>
            <td>Static site does not require server support</td>
            <td>Simple information only website.</td>
  <td></td>
        </tr>
        <tr>
            <td>Level 1</td>
            <td>Rich UI with server support. Data is typically stored on the server side.  The server provides rich search services. Do not require special services.</td>
            <td>Basic HTML5, CSS, XML and Javascript</td>
            <td>Most web applications fit this category.</td>
        </tr>
        <tr>
            <td>Level 2</td>
            <td>Same as Level 1 but require additional speical services to be built.   </td>
            <td>The URL address to the remote WSDL file.</td>
  <td></td>
        </tr>
        <tr>
            <td>Level 3</td>
            <td>Same as Level 2 but require additional big data processing . </td>
            <td>The URL address to the remote WSDL file.</td>
  <td></td>
        </tr>
</table>


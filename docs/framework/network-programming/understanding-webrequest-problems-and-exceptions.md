---
title: "Informaci&#243;n acerca de los problemas y excepciones del elemento WebRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Informaci&#243;n acerca de los problemas y excepciones del elemento WebRequest
<xref:System.Net.WebRequest> y sus clases derivadas \(<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, y <xref:System.Net.FileWebRequest>\) producen excepciones para designar una condición irregular.  La resolución de estos problemas no a veces es evidente.  
  
## Soluciones  
 Examine la propiedad de <xref:System.Net.WebException.Status%2A> de <xref:System.Net.WebException> para determinar el problema.  La tabla siguiente muestra varios valores de estado y algunas posibles soluciones.  
  
|Estado|Detalles|Soluciones|  
|------------|--------------|----------------|  
|<xref:System.Net.WebExceptionStatus><br /><br /> O bien<br /><br /> <xref:System.Net.WebExceptionStatus>|Hay un problema con el socket subyacente.  La conexión puede haber sido restaurada.|Vuelva a conectar y reenvíe la solicitud.<br /><br /> Asegúrese de que el último Service Pack instalado.<br /><br /> Aumente el valor de la propiedad de <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName> .<br /><br /> Establezca <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName> en `false`.<br /><br /> Aumente el número de conexiones máximas con la propiedad de <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> .<br /><br /> Compruebe la configuración del proxy.<br /><br /> Si utiliza SSL, asegúrese de que el proceso de servidor tiene permiso de acceso al almacén de certificados.<br /><br /> Si envía una gran cantidad de datos, establezca <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> a `false`.|  
|<xref:System.Net.WebExceptionStatus>|El certificado de servidor no puede validarse.|Intente abrir el URI mediante Internet Explorer.  Resuelva cualquier alerta de seguridad mostrada por IE.  Si no puede resolver la alerta de seguridad, puede crear una clase de directiva de certificados que implemente <xref:System.Net.ICertificatePolicy> que devuelve `true`, y lo pasa a <xref:System.Net.ServicePointManager.CertificatePolicy%2A>.<br /><br /> Consulte [http:\/\/support.microsoft.com\/?id\=823177](http://go.microsoft.com/fwlink/?LinkID=179653).<br /><br /> Asegúrese de que el certificado de la entidad de certificación que firmó el certificado de servidor se agrega a la lista de entidades de certificación de confianza en Internet Explorer.<br /><br /> Asegúrese de que coincida con el nombre de host en la dirección URL el nombre común del certificado de servidor.|  
|<xref:System.Net.WebExceptionStatus>|Un error en la transacción de SSL, o hay un problema de certificado.|La versión 1,1 de .NET Framework admite únicamente la versión 3,0 de SSL.  Si el servidor se utiliza sólo la versión 1,0 de TLS o la versión 2,0 de SSL, se produce una excepción.  Actualice a .NET Framework la versión 2,0 y, a <xref:System.Net.ServicePointManager.SecurityProtocol%2A> establecido para coincidir con el servidor.<br /><br /> El certificado de cliente se firmado por una entidad de certificación \(CA\) que el servidor no depende.  Instale el certificado de una entidad de certificación en el servidor.  Vea [http:\/\/support.microsoft.com\/?id\=332077](http://go.microsoft.com/fwlink/?LinkID=179654).<br /><br /> Asegúrese de que hacer el último Service Pack instalado.|  
|<xref:System.Net.WebExceptionStatus>|Error en la conexión.|Firewall o un proxy está bloqueando la conexión.  Modifique el firewall o el proxy para permitir la conexión.<br /><br /> Explícitamente señale <xref:System.Net.WebProxy> en la aplicación cliente llamando al constructor de <xref:System.Net.WebProxy> \(WebServiceProxyClass.Proxy \= nuevos WebProxy \([http:\/\/server:80](http://server/), true\)\).<br /><br /> Ejecute Filemon o Regmon para garantizar que la identidad del proceso de trabajo tiene los permisos necesarios para tener acceso a WSPWSP.dll, a HKLM \\ al sistema \\ a CurrentControlSet \\ en Servicios \\ a DnsCache o HKLM \\ sistema \\ CurrentControlSet \\ Services \\ WinSock2.|  
|<xref:System.Net.WebExceptionStatus>|El Servicio de nombres de dominio no puede resolver el nombre de host.|Configure el proxy correctamente.  Vea [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Asegúrese de que ningún software antivirus instalado o firewall no está bloqueando la conexión.|  
|<xref:System.Net.WebExceptionStatus>|<xref:System.Net.WebRequest.Abort%2A> se llamó a, o un error ha producido.|Este problema se puede producir por una carga pesada en el cliente o el servidor.  Reduzca la carga.<br /><br /> Aumente el valor de <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> .<br /><br /> Vea [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) para modificar la configuración de rendimiento del servicio web.|  
|<xref:System.Net.WebExceptionStatus>|La aplicación intentó escribir un socket que se ha cerrado ya.|Sobrecargan el cliente o el servidor.  Reduzca la carga.<br /><br /> Aumente el valor de <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> .<br /><br /> Vea [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) para modificar la configuración de rendimiento del servicio web.|  
|<xref:System.Net.WebExceptionStatus>|El límite establecido \(<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\) de longitud de mensaje se superó.|Aumente el valor de la propiedad de <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A> .|  
|<xref:System.Net.WebExceptionStatus>|El Servicio de nombres de dominio no puede resolver el nombre de host de proxy.|Configure el proxy correctamente.  Vea [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> Fuerza <xref:System.Net.HttpWebRequest> para no utilizar ningún proxy estableciendo la propiedad de <xref:System.Net.HttpWebRequest.Proxy%2A> a `null`.|  
|<xref:System.Net.WebExceptionStatus>|La respuesta del servidor no es una respuesta HTTP válida.  Este problema se produce cuando .NET Framework detecta que la respuesta del servidor no cumple el HTTP 1,1 RFC.  Este problema puede producirse cuando la respuesta contiene encabezados incorrectos o encabezado incorrecto delimiters.RFC 2616 define el HTTP 1,1 y el formato válido para la respuesta del servidor.  Para obtener más información, vea [http:\/\/www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388).|Obtenga un seguimiento de red de la transacción y examine los encabezados de la respuesta.<br /><br /> Si la aplicación requiere la respuesta del servidor sin analizar \(puede ser un problema de seguridad\), establezca `useUnsafeHeaderParsing` a `true` en el archivo de configuración.  Vea [\<httpWebRequest\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md).|  
  
## Vea también  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>
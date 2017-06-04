---
title: "Cambios en la autenticaci&#243;n NTLM para HttpWebRequest en la versi&#243;n 3.5 SP1 | Microsoft Docs"
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
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Cambios en la autenticaci&#243;n NTLM para HttpWebRequest en la versi&#243;n 3.5 SP1
Los cambios de seguridad se realizaron en la versión 3,5 SP1 de .NET Framework y más adelante esa afecta a cómo la autenticación de Windows integrada controla <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream>, y las clases relacionadas en el espacio de nombres System.Net.  Estos cambios pueden afectar a las aplicaciones que utilizan estas clases para hacer solicitudes web y recibir respuestas donde la autenticación de Windows integrada basada en NTLM se utiliza.  Este cambio puede afectar servidores web y las aplicaciones cliente que se configuran para usar la autenticación de Windows integrada.  
  
## Información general  
 El diseño de autenticación de Windows integrada permite que algunas respuestas credenciales son universal, lo que significa que se puede reutilizar o ser reenviado.  Si esta característica de diseño determinada no es necesaria, los protocolos de autenticación deben contener información específica de destino así como canalizarse información específica.  Los servicios pueden proporcionar protección extendida para garantizar que las respuestas credenciales contienen información específica del servicio como una entidad de seguridad Name \(SPN\) del servicio.  Con esta información en los intercambios credenciales, los servicios pueden proteger mejor contra el uso malintencionado de las respuestas credenciales que podrían incorrectamente haberse obtenidas.  
  
 Varios componentes en <xref:System.Net> y espacios de nombres de <xref:System.Net.Security> realizan la autenticación de Windows integrada en nombre de una aplicación de llamada.  Esta sección describe los cambios en los componentes de System.Net para agregar protección extendida en el uso de la autenticación de Windows integrada.  
  
## Cambios  
 El proceso de autenticación NTLM utilizado con la autenticación de Windows integrada incluye un desafío emitido por el equipo de destino y el posterior enviado al equipo cliente.  Cuando un equipo recibe un desafío que se generó, la autenticación se producirá un error a menos que la conexión es un bucle \- conexión posterior \(dirección IPv4 127.0.0.1, por ejemplo\).  
  
 Al tener acceso a la ejecución de un servicio en un servidor web interno, suelen tener acceso al servicio mediante una dirección URL similar a http:\/\/contoso\/service o https:\/\/contoso\/service.  El nombre “contoso” no suele ser el nombre del equipo en el que se implementa el servicio.  <xref:System.Net> y compatibilidad relacionado de los espacios de nombres mediante Active Directory, DNS, NetBIOS, el archivo de hosts local \(normalmente WINDOWS \\ system32 \\ controladores \\ etc. \\ host, por ejemplo\), o archivo del lmhosts del equipo local \(normalmente WINDOWS \\ system32 \\ controladores \\ etc. \\ lmhosts, por ejemplo\) para resolver nombres a las direcciones.  Se resuelve el nombre “contoso” para enviar las solicitudes enviadas a “contoso” en el equipo servidor adecuado.  
  
 Cuando está configurado para las implementaciones grandes, también es común que un nombre de servidor virtual es determinado a la implementación con los nombres de equipo subyacentes nunca utilizados por aplicaciones cliente y usuarios finales.  Por ejemplo, puede llamar al servidor www.contoso.com, pero en un uso “contoso” de la red interna simplemente.  Este nombre se denomina el encabezado host de la solicitud web de cliente.  Como se especifica en el protocolo HTTP, el campo de encabezado de solicitud de host especifica el host de Internet y el número de puerto del recurso que se está solicitando.  Esta información se obtiene de URI original especificado por el usuario o el recurso de referencia \(normalmente dirección URL HTTP\).  En .NET Framework versión 4 Beta 2, esta información también se puede establecer al cliente utilizando la nueva propiedad de <xref:System.Net.HttpWebRequest.Host%2A> .  
  
 La clase de <xref:System.Net.AuthenticationManager> controla los componentes administrados de autenticación \(“módulos”\) usados por las clases derivadas de <xref:System.Net.WebRequest> y la clase de <xref:System.Net.WebClient> .  La clase de <xref:System.Net.AuthenticationManager> proporciona una propiedad que expone un objeto de <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName> , indizada por la cadena URI, porque las aplicaciones de proporcionar una cadena de custom SPN que se usará durante la autenticación.  
  
 La versión 3.5 SP1 ahora tiene como valor predeterminado especificar el nombre de host utilizado en la dirección URL de la solicitud en el SPN en el intercambio de autenticación de NTLM \(NT LAN Manager\) cuando no se establece la propiedad <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>.  El nombre de host utilizado en la dirección URL de la solicitud puede ser diferente del encabezado de host especificado en <xref:System.Net.HttpRequestHeader?displayProperty=fullName> en la solicitud de cliente.  El nombre de host utilizado en la dirección URL de la solicitud puede ser diferente del nombre de host real del servidor, el nombre de equipo del servidor, la dirección IP del equipo o la dirección de bucle invertido.  En estos casos, Windows producirá un error en la solicitud de autenticación.  Para resolver el problema, es necesario notificar a Windows que el nombre de host utilizado en la dirección URL de la solicitud en la solicitud de cliente \(“contoso”, por ejemplo\) es realmente un nombre alternativo para el equipo local.  
  
 Hay varios métodos posibles para que una aplicación de servidor funcione para este cambio.  El enfoque recomendado es asignar el nombre de host utilizado en la dirección URL de la solicitud a la clave de `BackConnectionHostNames` en el registro en el servidor.  La clave del Registro de `BackConnectionHostNames` se utiliza normalmente para asignar un nombre de host a una dirección de bucle invertido.  Los pasos se enumeran.  
  
 Para especificar los nombres de host que se asignan a la dirección de bucle invertido y pueden conectarse a sitios Web en un equipo local, siga estos pasos:  
  
 1.  Haga clic en Inicio y en Ejecutar, escriba regedit y, a continuación, haga clic en Aceptar.  
  
 2.  En el Editor del Registro, busque y haga clic en la clave del Registro siguiente:  
  
 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`  
  
 3.  Haga clic con MSV1\_0, elija Nuevo, haga clic en el valor de la cadena múltiple.  
  
 4.  Escriba `BackConnectionHostNames` y presione ENTRAR.  
  
 5.  Haga clic con `BackConnectionHostNames`, y haga clic en Modificar.  
  
 6.  En los datos del valor encajone, escriba el nombre de host o nombres de host para los sitios \(el nombre de host utilizado en la dirección URL de la solicitud\) que está en el equipo local, y haga clic en.  
  
 7.  Deje el Editor del Registro, y reinicie el servicio y ejecución IISReset de IISAdmin.  
  
 Un trabajo menos seguro alrededor es deshabilitar el bucle \- comprobación posteriores, como se describe en. [http:\/\/support.microsoft.com\/kb\/896861](http://go.microsoft.com/fwlink/?LinkID=179657) Esto deshabilita la protección contra los ataques de reflexión.  Es tan mejor restringir el conjunto de nombres alternativos sólo a los que se espera que el equipo utiliza realmente.  
  
## Vea también  
 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName>   
 <xref:System.Net.HttpRequestHeader?displayProperty=fullName>   
 <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=fullName>
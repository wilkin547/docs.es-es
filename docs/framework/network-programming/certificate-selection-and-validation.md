---
title: "Selecci&#243;n y validaci&#243;n de certificados | Microsoft Docs"
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
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Selecci&#243;n y validaci&#243;n de certificados
Las clases de <xref:System.Net> admiten varias maneras de seleccionar y de validar <xref:System.Security.Cryptography.X509Certificates> para las conexiones de \(SSL\) de Capa de sockets seguros.  Un cliente puede seleccionar uno o varios certificados para autenticarse a un servidor.  Un servidor puede requerir que un certificado de cliente tiene uno o más atributos específicos de la autenticación.  
  
## Definición  
 Un certificado es un byte ASCII transmitir que contiene una clave pública, atributos \(como el número de versión, número de serie, y fecha de expiración\) y una firma digital de una entidad de certificación.  Los certificados se utilizan para establecer una conexión cifrada o para autenticar un cliente a un servidor.  
  
## Selección y validación de certificado de cliente  
 Un cliente puede seleccionar uno o varios certificados para una conexión específica de SSL.  Los certificados de cliente se pueden asociar a la conexión SSL en un servidor web o en un servidor de correo SMTP.  Un cliente agrega los certificados a una colección de <xref:System.Security.Cryptography.X509Certificates.X509Certificate> u objetos de la clase de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> .  Mediante correo electrónico como ejemplo, la colección de certificados es una instancia de <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>\) asociado a la propiedad de <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> de la clase de <xref:System.Net.Mail.SmtpClient> .  La clase de <xref:System.Net.HttpWebRequest> tiene una propiedad similar de <xref:System.Net.HttpWebRequest.ClientCertificates%2A> .  
  
 La principal diferencia entre <xref:System.Security.Cryptography.X509Certificates.X509Certificate> y la clase de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> es que la clave privada debe residir en el almacén de certificados para la clase de <xref:System.Security.Cryptography.X509Certificates.X509Certificate> .  
  
 Aunque los certificados se agregan a una colección y están asociados a una conexión concreta de SSL, no se enviará ningún certificados el servidor a menos que el servidor los solicite.  Si los certificados de cliente varios se establecen en una conexión, la mejor se utilizará según un algoritmo que considere la coincidencia entre la lista de emisores de certificados proporcionados por el servidor y el nombre del emisor del certificado de cliente.  
  
 La clase de <xref:System.Net.Security.SslStream> proporciona aún más el control de manos de SSL.  Un cliente puede especificar un delegado para selección que el certificado de cliente a utilizar.  
  
 Un servidor remoto puede comprobar que un certificado de cliente es válido, actual, y firmado por la autoridad adecuada.  Un delegado puede agregarse a <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> para exigir la validación de certificados.  
  
## Selección de certificados de cliente  
 .NET Framework selecciona el certificado de cliente para mostrar el servidor de la manera siguiente:  
  
1.  Si un certificado de cliente se mostraron previamente el servidor, se almacena en caché la primera vez que se muestra y se reutiliza el certificado para las solicitudes subsiguientes del certificado de cliente.  
  
2.  Si un delegado está presente, utilice siempre el resultado del delegado como el certificado de cliente para seleccionar.  Intente utilizar un certificado almacenado en caché cuando es posible, pero no utilice credenciales anónimas almacenadas en caché si el delegado ha devuelto null y la colección de certificado no está vacía.  
  
3.  Si éste es el primer desafío para un certificado de cliente, el marco enumera los certificados en <xref:System.Security.Cryptography.X509Certificates.X509Certificate> o los objetos de la clase de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> asociados a la conexión, buscar una coincidencia entre la lista de emisores de certificados proporcionados por el servidor y el nombre del emisor del certificado de cliente.  El primer certificado que coincida se envía al servidor.  Si coincide ningún certificado o la colección de certificado está vacía, después una credencial anónima se envía al servidor.  
  
## Herramientas para la configuración de certificados  
 Varias herramientas están disponibles para la configuración del cliente y del certificado de servidor.  
  
 La herramienta de *Winhttpcertcfg.exe* se puede utilizar para configurar los certificados de cliente.  La herramienta de *Winhttpcertcfg.exe* se proporciona como una herramientas el kit de recursos de Windows Server 2003.  Esta herramienta también está disponible como descarga como parte del recurso Kit Tools de Windows Server 2003 en www.microsoft.com.  
  
 La herramienta de*El HttpCfg.exe* se puede utilizar para configurar los certificados de servidor para la clase de <xref:System.Net.HttpListener> .  La herramienta de *HttpCfg.exe* se proporciona como una de las herramientas de soporte de Windows Server 2003 y Windows XP Service Pack 2.  El*HttpCfg.exe* y las otras herramientas de soporte no se instalan de forma predeterminada en Windows Server 2003 o Windows XP.  En Windows Server 2003.  las herramientas de soporte se instalan independientemente de la carpeta y archivo siguientes en Windows Server 2003 CD\-ROM:  
  
 \\ Compatibilidad \\ herramientas \\ Suptools.msi  
  
 Para el uso con Windows XP Service Pack 2, las herramientas de soporte de Windows XP están disponibles como descarga de www.microsoft.com.  
  
 El código fuente a una versión de la herramienta de *HttpCfg.exe* también se proporciona como ejemplo Windows Server SDK.  El código fuente del ejemplo de *HttpCfg.exe* se instala de forma predeterminada con los ejemplos de red como parte de Windows SDK bajo la carpeta siguiente:  
  
 *C:\\Program Files\\Microsoft SDKs\\Windows\\v1.0\\Samples\\NetDS\\http\\serviceconfig*  
  
 Además de estas herramientas, las clases de <xref:System.Security.Cryptography.X509Certificates.X509Certificate> y de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> proporcionan métodos para cargar un certificado en el sistema de archivos.  
  
## Vea también  
 [Seguridad en la programación para redes](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)
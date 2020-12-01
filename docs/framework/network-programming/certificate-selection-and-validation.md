---
title: Selección y validación de certificados
description: Obtenga información sobre las distintas formas ofrecidas por las clases System.Net para seleccionar y validar certificados de conexión SSL/TLS.
ms.date: 03/30/2017
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
ms.openlocfilehash: a85b6947c20f7dbced1fb6ad6e79f3134ce1f57b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287519"
---
# <a name="certificate-selection-and-validation"></a>Selección y validación de certificados

Las clases <xref:System.Net> admiten varios métodos para seleccionar y validar <xref:System.Security.Cryptography.X509Certificates> para conexiones de Capa de sockets seguros (SSL). Un cliente puede seleccionar uno o varios certificados para autenticarse en un servidor. Un servidor puede requerir que un certificado de cliente tenga uno o más atributos específicos para la autenticación.  
  
## <a name="definition"></a>Definición  

 Un certificado es un flujo de bytes ASCII que contiene una clave pública, atributos (por ejemplo, el número de versión, el número de serie y la fecha de expiración) y una firma digital de una entidad de certificación. Los certificados se usan para establecer una conexión cifrada o para autenticar un cliente en un servidor.  
  
## <a name="client-certificate-selection-and-validation"></a>Selección y validación de certificados de cliente  

 Un cliente puede seleccionar uno o varios certificados para una conexión SSL concreta. Los certificados de cliente se pueden asociar con la conexión SSL a un servidor web o un servidor de correo SMTP. Un cliente agrega certificados a una colección de objetos de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate> o <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>. Si se usa el correo electrónico como ejemplo, la colección de certificados es una instancia de un elemento <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>) asociado a la propiedad <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> de la clase <xref:System.Net.Mail.SmtpClient>. La clase <xref:System.Net.HttpWebRequest> tiene una propiedad <xref:System.Net.HttpWebRequest.ClientCertificates%2A> similar.  
  
 La diferencia principal entre la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate> y <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> es que la clave privada debe residir en el almacén de certificados de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate>.  
  
 Aunque se agreguen certificados a una colección y se asocien a una conexión SSL concreta, no se enviará ningún certificado al servidor a menos que este lo solicite. Si se establecen varios certificados de cliente en una conexión, se usará el mejor según un algoritmo que considera la coincidencia entre la lista de emisores de certificados proporcionados por el servidor y el nombre del emisor del certificado de cliente.  
  
 La clase <xref:System.Net.Security.SslStream> proporciona aún más control sobre el protocolo de enlace SSL. Un cliente puede especificar un delegado para elegir qué certificado de cliente va a usar.  
  
 Un servidor remoto puede comprobar que un certificado de cliente es válido, actual y está firmado por la entidad de certificación adecuada. Se puede agregar un delegado a <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> para exigir la validación del certificado.  
  
## <a name="client-certificate-selection"></a>Selección de certificado de cliente  

 .NET Framework selecciona el certificado de cliente que va a presentar al servidor de la siguiente manera:  
  
1. Si se ha presentado un certificado de cliente anteriormente al servidor, el certificado se almacena en caché cuando se presenta por primera vez y se vuelve a usar para las solicitudes de certificado de cliente posteriores.  
  
2. Si hay un delegado, use siempre el resultado del delegado como certificado de cliente para seleccionar. Intente usar un certificado almacenado en caché siempre que sea posible, pero no use credenciales anónimas almacenadas en caché si el delegado ha devuelto null y la colección de certificados no está vacía.  
  
3. Si este es el primer desafío de un certificado de cliente, el marco de trabajo enumera los certificados de los objetos de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate> o <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> asociados a la conexión y busca una coincidencia entre la lista de emisores de certificados proporcionados por el servidor y el nombre del emisor del certificado de cliente. El primer certificado que coincida se envía al servidor. Si ningún certificado coincide o la colección de certificados está vacía, se envía una credencial anónima al servidor.  
  
## <a name="tools-for-certificate-configuration"></a>Herramientas para la configuración de certificados  

 Hay varias herramientas disponibles para la configuración de certificados de cliente y servidor.  
  
 La herramienta *Winhttpcertcfg.exe* puede usarse para configurar certificados de cliente. La herramienta *Winhttpcertcfg.exe* es una de las herramientas del Kit de recursos de Windows Server 2003. Esta herramienta también está disponible como descarga como parte de las herramientas del Kit de recursos de Windows Server 2003 en [www.microsoft.com](https://www.microsoft.com).  
  
La herramienta *HttpCfg.exe* se puede usar para configurar certificados de servidor para la clase <xref:System.Net.HttpListener>. La herramienta *HttpCfg.exe* es una de las herramientas de soporte de Windows Server 2003 y Windows XP Service Pack 2. *HttpCfg.exe* y las demás herramientas de soporte no se instalan de forma predeterminada ni en Windows Server 2003 ni en Windows XP. En Windows Server 2003, las herramientas de soporte se instalan por separado desde la carpeta y el archivo siguientes del CD-ROM de Windows Server 2003:  
  
 \Support\Tools\Suptools.msi  
  
 Para su uso con Windows XP Service Pack 2, las herramientas de soporte de Windows XP están disponibles como descarga en [www.microsoft.com](https://www.microsoft.com).  
  
 El código fuente para una versión de la herramienta *HttpCfg.exe* también se proporciona como ejemplo con el SDK de Windows Server. El código fuente para el ejemplo *HttpCfg.exe* se instala de forma predeterminada con los ejemplos de redes como parte de Windows SDK en la siguiente carpeta:  
  
 *C:\Archivos de programa\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig*  
  
 Además de estas herramientas, las clases <xref:System.Security.Cryptography.X509Certificates.X509Certificate> y <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> proporcionan métodos para cargar un certificado desde el sistema de archivos.  
  
## <a name="see-also"></a>Vea también

- [Seguridad en la programación para redes](security-in-network-programming.md)
- [Programación para redes en .NET Framework](index.md)

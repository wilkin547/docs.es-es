---
title: "C&#243;mo: especificar las credenciales de cliente para una solicitud de servicio de datos (Servicio de datos de WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Servicios de datos de Microsoft WCF, personalizar solicitudes"
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: especificar las credenciales de cliente para una solicitud de servicio de datos (Servicio de datos de WCF)
De forma predeterminada, la biblioteca cliente no proporciona credenciales cuando se envía una solicitud a un servicio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Sin embargo, puede especificar que las credenciales se envíen para autenticar solicitudes al servicio de datos proporcionando una clase <xref:System.Net.NetworkCredential> para la propiedad <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>.  Para obtener más información, consulta [Proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  En el ejemplo de este tema se muestra cómo proporcionar explícitamente credenciales que el cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usará cuando solicite datos del servicio de datos.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Además puede usar el [servicio de datos de ejemplo Northwind](http://go.microsoft.com/fwlink/?LinkId=187426) que se publica en el sitio web de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Este servicio de datos de ejemplo es de solo lectura y si se intentan guardar los cambios, devuelve un error.  Los servicios de datos de ejemplo del sitio web de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] permiten la autenticación anónima.  
  
## Ejemplo  
 El siguiente ejemplo proviene una página de codigos subyacente de un archivo de lenguaje XAML que es la página principal de la aplicación de Windows Presentation Framework.  En este ejemplo se muestra una instancia de `LoginWindow` para recopilar las credenciales de autenticación del usuario y, a continuación, las usa cuando realiza una solicitud al servicio de datos.  
  
  
  
## Ejemplo  
 El código XAML siguiente define la página principal de la aplicación WPF.  
  
  
  
## Ejemplo  
 El siguiente ejemplo proviene de la página de codigos subyacente de la ventana que se usa para recopilar las credenciales de autenticación del usuario antes de realizar una solicitud al servicio de datos.  
  
  
  
## Ejemplo  
 El código XAML siguiente define el inicio de sesión de la aplicación WPF.  
  
  
  
## Seguridad de .NET Framework  
 Las siguientes consideraciones de seguridad son aplicables al ejemplo de este tema:  
  
-   Para comprobar que funcionan las credenciales proporcionadas en este ejemplo, el servicio de datos de Northwind debe usar un esquema de autenticación que no sea de acceso anónimo.  De lo contrario, el sitio web que hospede el servicio de datos no solicitará las credenciales.  
  
-   Las credenciales de usuario solo se deben solicitar durante la ejecución y no se deben almacenar en memoria caché.  Las credenciales se deben almacenar siempre de forma segura.  
  
-   Los datos enviados con la autenticación básica e implícita no se cifran. Por tanto, los puede ver un adversario.  Además, se envían credenciales de autenticación básica \(nombre de usuario y contraseña\) en texto no cifrado y se pueden interceptar.  
  
 Para obtener más información, consulta [Proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## Vea también  
 [Proteger WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
---
title: Filtrar Especifique las credenciales del cliente para un servicio de datos de solicitud (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: ca2ed1fcf113e06535c8900e5836eb64f9b23958
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2019
ms.locfileid: "59518141"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>Filtrar Especifique las credenciales del cliente para un servicio de datos de solicitud (WCF Data Services)
De forma predeterminada, la biblioteca cliente no proporciona credenciales cuando se envía una solicitud a un servicio [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Sin embargo, puede especificar que las credenciales se envíen para autenticar solicitudes al servicio de datos proporcionando una clase <xref:System.Net.NetworkCredential> para la propiedad <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>. Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). En el ejemplo de este tema se muestra cómo proporcionar explícitamente credenciales que el cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usará cuando solicite datos del servicio de datos.  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean cuando se completa la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). También puede usar el [servicio de datos de ejemplo Northwind](https://go.microsoft.com/fwlink/?LinkId=187426) que se publica en el [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ; estos datos de ejemplo de sitio Web de servicio es de solo lectura y se intentan guardar los cambios devuelve un error. Los datos de ejemplo de servicios en la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sitio Web de permitir la autenticación anónima.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es desde la página de código subyacente de un archivo de lenguaje de marcado de aplicaciones Extensible (XAML) que es la página principal de la aplicación de Windows Presentation Framework. En este ejemplo se muestra una instancia de `LoginWindow` para recopilar las credenciales de autenticación del usuario y, a continuación, las usa cuando realiza una solicitud al servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente define la página principal de la aplicación WPF.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo proviene de la página de codigos subyacente de la ventana que se usa para recopilar las credenciales de autenticación del usuario antes de realizar una solicitud al servicio de datos.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente define el inicio de sesión de la aplicación WPF.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Las siguientes consideraciones de seguridad son aplicables al ejemplo de este tema:  
  
-   Para comprobar que funcionan las credenciales proporcionadas en este ejemplo, el servicio de datos de Northwind debe usar un esquema de autenticación que no sea de acceso anónimo. De lo contrario, el sitio web que hospede el servicio de datos no solicitará las credenciales.  
  
-   Las credenciales de usuario solo se deben solicitar durante la ejecución y no se deben almacenar en memoria caché. Las credenciales se deben almacenar siempre de forma segura.  
  
-   Los datos enviados con la autenticación básica e implícita no se cifran. Por tanto, los puede ver un adversario. Además, se envían credenciales de autenticación básica (nombre de usuario y contraseña) en texto no cifrado y se pueden interceptar.  
  
 Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Protección de WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

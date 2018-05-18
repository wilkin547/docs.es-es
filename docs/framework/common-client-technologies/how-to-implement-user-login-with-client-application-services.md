---
title: 'Cómo: Implementar el inicio de sesión de usuarios con servicios de aplicaciones cliente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
ms.openlocfilehash: 1b1c5bebb5bd94f0a56dc6da303ef2503ab6dd4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-implement-user-login-with-client-application-services"></a>Cómo: Implementar el inicio de sesión de usuarios con servicios de aplicaciones cliente
Puede usar servicios de aplicaciones cliente para validar usuarios a través de un servicio de perfiles de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] existente. Para información sobre cómo configurar el servicio de perfiles de [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], vea [Usar la autenticación de formularios con Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).  
  
 Los procedimientos siguientes describen cómo validar usuarios a través del servicio de autenticación cuando la aplicación está configurada para usar uno de los proveedores de servicios de autenticación de cliente. Para obtener más información, consulte [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Normalmente realizará toda la validación a través del método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>. Este método administra la interacción con el servicio de autenticación a través del proveedor de autenticación configurado. Para más información, consulte [Información general sobre los servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
 Los procedimientos de autenticación de formularios requieren acceso a un servicio de autenticación [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] en ejecución. Para obtener orientación sobre las pruebas de un punto de conexión a otro de las características de los servicios de aplicaciones cliente, vea [Tutorial: Usar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a>Para autenticar un usuario con autenticación de formularios mediante un proveedor de credenciales de pertenencia  
  
1.  Implementar la interfaz <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>. El siguiente ejemplo de código muestra una implementación de <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> para una clase de cuadro de diálogo de inicio de sesión derivada de <xref:System.Windows.Forms.Form?displayProperty=nameWithType>. Este cuadro de diálogo tiene cuadros de texto para el nombre de usuario y la contraseña y una casilla «Recordar mi cuenta». Cuando el proveedor de autenticación del cliente llama al método <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>, se muestra el formulario. Cuando el usuario escribe la información en el cuadro de diálogo de inicio de sesión y hace clic en Aceptar, los valores especificados se devuelven en un nuevo objeto <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  Llame al método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> y pase cadenas vacías como valores de parámetro. Al especificar cadenas vacías, este método llama internamente al método <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A> del proveedor de credenciales configurado para la aplicación. En el ejemplo de código siguiente se llama a este método para restringir el acceso a toda una aplicación de formularios Windows Forms. Puede agregar este código a un controlador <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a>Para autenticar un usuario con autenticación de formularios sin usar un proveedor de credenciales de pertenencia  
  
-   Llame al método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> y pase los valores de nombre de usuario y contraseña recuperados del usuario.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a>Para autenticar un usuario con autenticación de Windows  
  
-   Llame al método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> y pase cadenas vacías para los parámetros. Esta llamada al método siempre devolverá `true` y agregará una cookie a la caché de cookies del usuario que contiene la identidad de Windows.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a>Programación sólida  
 El código de ejemplo de este tema muestra los usos más simples de la autenticación en una aplicación cliente de Windows. Pero cuando se llama al método `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> con servicios de aplicación cliente y la autenticación de formularios, el código puede iniciar una <xref:System.Net.WebException>. Esto indica que el servicio de autenticación no está disponible. Para obtener un ejemplo de cómo controlar esta excepción, vea [Tutorial: Usar servicios de aplicaciones clientes](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Servicios de aplicación cliente](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Información general sobre los servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Cómo: Configurar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Tutorial: Usar servicios de aplicaciones cliente](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Utilizar la autenticación de formularios con AJAX en ASP.NET](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)

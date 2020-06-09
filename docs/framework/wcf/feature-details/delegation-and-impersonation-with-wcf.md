---
title: Delegación y suplantación con WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- impersonation [WCF]
- delegation [WCF]
ms.assetid: 110e60f7-5b03-4b69-b667-31721b8e3152
ms.openlocfilehash: e491925fdbe8d44df8e0c64b563eb92569453e35
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599261"
---
# <a name="delegation-and-impersonation-with-wcf"></a>Delegación y suplantación con WCF
La*suplantación* es una técnica habitual que utilizan los servicios para restringir el acceso de los clientes a los recursos de un dominio de servicio. Los recursos de dominio de servicio pueden ser recursos de equipo, como archivos locales (suplantación), o un recurso en otro equipo, como un recurso compartido de archivos (delegación). Para obtener una aplicación de ejemplo, consulte [Impersonating the Client](../samples/impersonating-the-client.md). Para obtener un ejemplo sobre el uso de la suplantación, consulte [How to: Impersonate a Client on a Service](../how-to-impersonate-a-client-on-a-service.md).  
  
> [!IMPORTANT]
> Tenga en cuenta que al suplantar un cliente en un servicio, éste se ejecuta con las credenciales del cliente, que puede tener privilegios más altos que el proceso del servidor.  
  
## <a name="overview"></a>Información general  
 Normalmente, los clientes llaman a un servicio para que éste realice alguna acción en representación de cliente. La suplantación permite al servicio actuar como el cliente cuando realiza la acción. La delegación permite a un servicio front-end enviar la solicitud del cliente a un servicio back-end de modo que éste también puede suplantar al cliente. La suplantación se utiliza habitualmente como modo de comprobar si un cliente está autorizado para realizar una acción concreta, mientras que la delegación es una manera de hacer fluir las funciones de suplantación, junto con la identidad del cliente, a un servicio back-end. La delegación es una característica del dominio de Windows que puede usarse al realizar una autenticación basada en Kerberos. La delegación es diferente al flujo de identidad y, dado que la delegación transfiere la capacidad de suplantación del cliente sin poseer su contraseña, es una operación que disfruta de privilegios más elevados que el flujo de identidad.  
  
 Tanta la suplantación como la delegación requieren que el cliente posea una identidad de Windows. Si el cliente no posee una identidad de Windows, la única opción disponible es hacer fluir la identidad del cliente hasta el segundo servicio.  
  
## <a name="impersonation-basics"></a>Fundamentos de la suplantación  
 Windows Communication Foundation (WCF) admite la suplantación para diversas credenciales de cliente. En este tema se describe la compatibilidad del modelo de servicio para suplantar al autor de la llamada durante la implementación de un método de servicio. También se describen los escenarios de implementación comunes que implican la suplantación y la seguridad de SOAP y las opciones de WCF en estos escenarios.  
  
 Este tema se centra en la suplantación y delegación en WCF cuando se usa la seguridad de SOAP. También puede usar la suplantación y delegación con WCF al usar la seguridad de transporte, como se describe en uso de la [suplantación con la seguridad de transporte](using-impersonation-with-transport-security.md).  
  
## <a name="two-methods"></a>Dos métodos  
 La seguridad de WCF SOAP tiene dos métodos distintos para realizar la suplantación. El método utilizado depende del enlace. El primero es la suplantación de un token de Windows obtenido desde la interfaz de proveedor de compatibilidad para seguridad (SSPI) o la autenticación de Kerberos, que se almacena en la memoria caché en el servicio. El segundo es la suplantación de un token de Windows obtenido a partir de las extensiones de Kerberos, denominado en su conjunto *servicio para usuario* (S4U).  
  
### <a name="cached-token-impersonation"></a>Suplantación del token almacenado en caché  
 Puede realizar la suplantación del token almacenado en caché con lo siguiente:  
  
- <xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>y <xref:System.ServiceModel.NetTcpBinding> con una credencial de cliente de Windows.  
  
- <xref:System.ServiceModel.BasicHttpBinding> con <xref:System.ServiceModel.BasicHttpSecurityMode> definido en la credencial <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> , o cualquier otro enlace estándar donde el cliente presenta una credencial del nombre de usuario que el servicio puede asignar a una cuenta válida de Windows.  
  
- Cualquier <xref:System.ServiceModel.Channels.CustomBinding> que utiliza una credencial de cliente de Windows con `requireCancellation` definido en `true`. (La propiedad está disponible en las clases siguientes: <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> , <xref:System.ServiceModel.Security.Tokens.SslSecurityTokenParameters> y <xref:System.ServiceModel.Security.Tokens.SspiSecurityTokenParameters> ). Si se utiliza una conversación segura en el enlace, también debe tener la `requireCancellation` propiedad establecida en `true` .  
  
- Cualquier <xref:System.ServiceModel.Channels.CustomBinding> donde el cliente presenta una credencial de nombre de usuario. Si se utiliza una conversación segura en el enlace, también debe tener la propiedad `requireCancellation` establecida en `true`.  
  
### <a name="s4u-based-impersonation"></a>Suplantación basada en S4U  
 Puede realizar la suplantación basada en S4U con lo siguiente:  
  
- <xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>y <xref:System.ServiceModel.NetTcpBinding> con una credencial de certificado de cliente que el servicio puede asignar a una cuenta de Windows válida.  
  
- Cualquier <xref:System.ServiceModel.Channels.CustomBinding> que utiliza una credencial de cliente de Windows con la propiedad `requireCancellation` definida en `false`.  
  
- Cualquier <xref:System.ServiceModel.Channels.CustomBinding> que utiliza un nombre de usuario o credencial de cliente de Windows y una conversación segura con la propiedad `requireCancellation` establecida en `false`.  
  
 Hasta qué punto el servicio puede suplantar al cliente depende de los privilegios que la cuenta de servicio contiene al intentar suplantar, el tipo de suplantación utilizado y posiblemente hasta qué punto el cliente permite la suplantación.  
  
> [!NOTE]
> Cuando el cliente y el servicio se están ejecutando en el mismo equipo y el cliente se está ejecutando bajo una cuenta del sistema (por ejemplo, `Local System` o `Network Service`), no se puede suplantar el cliente cuando una sesión segura se establece con tokens de contexto de seguridad con estado. Una aplicación Windows Form o de consola se ejecutan normalmente con la cuenta con la que haya iniciado la sesión, de manera que la cuenta pueda suplantarse de manera predeterminada. Sin embargo, cuando el cliente es una página de ASP.NET y esa página se hospeda en IIS 6,0 o IIS 7,0, el cliente se ejecuta en la `Network Service` cuenta de forma predeterminada. Todos los enlaces proporcionados por el sistema que admiten sesiones seguras utilizan de forma predeterminada un token de contexto de seguridad sin estado (SCT). Sin embargo, si el cliente es una página de ASP.NET y se usan sesiones seguras con SCT con estado, el cliente no se puede suplantar. Para obtener más información sobre el uso de SCT con estado en una sesión segura, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
## <a name="impersonation-in-a-service-method-declarative-model"></a>Suplantación en un método de servicio: modelo declarativo  
 La mayoría de los escenarios de suplantación implican la ejecución del método de servicio en el contexto del autor de llamada. WCF proporciona una característica de suplantación que facilita esta tarea, ya que permite al usuario especificar el requisito de suplantación en el <xref:System.ServiceModel.OperationBehaviorAttribute> atributo. Por ejemplo, en el código siguiente, la infraestructura de WCF suplanta al llamador antes de ejecutar el `Hello` método. Cualquier intento para tener acceso a los recursos nativos dentro del método `Hello` solo tiene éxito si la lista de control de acceso (ACL) del recurso permite privilegios de acceso al autor de la llamada. Para habilitar la suplantación, establezca la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> en uno de los valores de enumeración <xref:System.ServiceModel.ImpersonationOption> , <xref:System.ServiceModel.ImpersonationOption.Required?displayProperty=nameWithType> o <xref:System.ServiceModel.ImpersonationOption.Allowed?displayProperty=nameWithType>, tal y como se muestra en el ejemplo siguiente.  
  
> [!NOTE]
> Cuando un servicio tiene las credenciales más altas que el cliente remoto, se utilizan las credenciales del servicio si la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> está establecida en <xref:System.ServiceModel.ImpersonationOption.Allowed>. Es decir, si un usuario con pocos privilegios proporciona sus credenciales, un servicio con más privilegios ejecuta el método con las credenciales del servicio y puede utilizar los recursos que el usuario con pocos privilegios no podría utilizar.  
  
 [!code-csharp[c_ImpersonationAndDelegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#1)]
 [!code-vb[c_ImpersonationAndDelegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#1)]  
  
 La infraestructura de WCF solo puede suplantar al autor de la llamada si el autor de la llamada se autentica con credenciales que se pueden asignar a una cuenta de usuario de Windows. Si el servicio se configura para autenticar utilizando una credencial que no puede estar asignada a una cuenta de Windows, no se ejecutará el método de servicio.  
  
> [!NOTE]
> En Windows XP, se produce un error en la suplantación si se crea un SCT con estado, lo que da como resultado una <xref:System.InvalidOperationException> . Para obtener más información, vea [escenarios no admitidos](unsupported-scenarios.md).  
  
## <a name="impersonation-in-a-service-method-imperative-model"></a>Suplantación en un método de servicio: modelo imperativo  
 En ocasiones, un autor de la llamada no necesita suplantar todo el método de servicio para funcionar, sino solo una parte de él. En este caso, obtenga la identidad de Windows del autor de la llamada dentro del método de servicio y realice la suplantación inmediatamente. Haga esto utilizando la propiedad <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> de <xref:System.ServiceModel.ServiceSecurityContext> para devolver una instancia de la clase <xref:System.Security.Principal.WindowsIdentity> y llamando al método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> antes de utilizar la instancia.  
  
> [!NOTE]
> Asegúrese de usar la instrucción Visual Basic `Using` o la instrucción de C# `using` para revertir automáticamente la acción de suplantación. Si no utiliza la instrucción, o si utiliza un lenguaje de programación distinto de Visual Basic o C#, asegúrese de revertir el nivel de suplantación. El no hacerlo puede ser la base de la denegación de servicio y aumentar los ataques contra los privilegios.  
  
 [!code-csharp[c_ImpersonationAndDelegation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#2)]
 [!code-vb[c_ImpersonationAndDelegation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#2)]  
  
## <a name="impersonation-for-all-service-methods"></a>Suplantación para todos los métodos de servicio  
 En algunos casos, debe realizar todos los métodos de un servicio en el contexto del autor de la llamada. En lugar de habilitar explícitamente esta característica por método, use la clase <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Tal y como se muestra en el código siguiente, defina la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A> en `true`. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> se recupera de las colecciones de comportamientos de la clase <xref:System.ServiceModel.ServiceHost> . Además, tenga en cuenta que la propiedad `Impersonation` de <xref:System.ServiceModel.OperationBehaviorAttribute> que se aplica a cada método debe definirse también en <xref:System.ServiceModel.ImpersonationOption.Allowed> o <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
 [!code-csharp[c_ImpersonationAndDelegation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#3)]
 [!code-vb[c_ImpersonationAndDelegation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#3)]  
  
 En la tabla siguiente se describe el comportamiento de WCF para todas las posibles combinaciones de `ImpersonationOption` y `ImpersonateCallerForAllServiceOperations` .  
  
|`ImpersonationOption`|`ImpersonateCallerForAllServiceOperations`|Comportamiento|  
|---------------------------|------------------------------------------------|--------------|  
|Obligatorio|N/D|WCF suplanta al autor de la llamada|  
|Permitida|false|WCF no suplanta al autor de la llamada|  
|Permitida|true|WCF suplanta al autor de la llamada|  
|No permitidos|false|WCF no suplanta al autor de la llamada|  
|No permitidos|true|No permitido. (Se produce una excepción <xref:System.InvalidOperationException> .)|  
  
## <a name="impersonation-level-obtained-from-windows-credentials-and-cached-token-impersonation"></a>Nivel de suplantación obtenido de las credenciales de Windows y la suplantación de tokens almacenados en caché  
 En algunos escenarios, el cliente tiene el control parcial sobre el nivel de suplantación que el servicio realiza cuando se utiliza una credencial de cliente de Windows. Se produce un escenario cuando el cliente especifica un nivel de suplantación anónimo. El otro se produce cuando se realiza la suplantación con un token en memoria caché. Esto se realiza estableciendo la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> de la clase <xref:System.ServiceModel.Security.WindowsClientCredential> , a la que se obtiene acceso como una propiedad de la clase <xref:System.ServiceModel.ChannelFactory%601> genérica.  
  
> [!NOTE]
> Especificar un nivel de suplantación de anónimo hace que el cliente inicie sesión anónimamente en el servicio. Por lo tanto, el servicio debe permitir inicios de sesión anónimos, sin tener en cuenta si se realiza la suplantación.  
  
 El cliente puede especificar el nivel de suplantación como <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>o <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. Se genera solo un token en el nivel especificado, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[c_ImpersonationAndDelegation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#4)]
 [!code-vb[c_ImpersonationAndDelegation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#4)]  
  
 La tabla siguiente especifica el nivel de suplantación que el servicio obtiene al suplantar un token almacenado en memoria caché.  
  
|Valor de`AllowedImpersonationLevel`|El servicio tiene `SeImpersonatePrivilege`|El servicio y el cliente tienen capacidad de delegación|`ImpersonationLevel`|  
|---------------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Anónimas|Sí|N/D|Suplantación|  
|Anónimas|No|N/D|Identificación|  
|Identificación|N/D|N/D|Identificación|  
|Suplantación|Sí|N/D|Suplantación|  
|Suplantación|No|N/D|Identificación|  
|Delegación|Sí|Sí|Delegación|  
|Delegación|Sí|No|Suplantación|  
|Delegación|No|N/D|Identificación|  
  
## <a name="impersonation-level-obtained-from-user-name-credentials-and-cached-token-impersonation"></a>Nivel de suplantación obtenido a partir de las credenciales de nombre de usuario y suplantación de token almacenado en caché  
 Al pasar el servicio a su nombre de usuario y contraseña, un cliente permite que WCF inicie sesión como ese usuario, lo que equivale a establecer la `AllowedImpersonationLevel` propiedad en <xref:System.Security.Principal.TokenImpersonationLevel.Delegation> . ( `AllowedImpersonationLevel` Está disponible en las <xref:System.ServiceModel.Security.WindowsClientCredential> clases y <xref:System.ServiceModel.Security.HttpDigestClientCredential> ). En la tabla siguiente se proporciona el nivel de suplantación obtenido cuando el servicio recibe credenciales de nombre de usuario.  
  
|`AllowedImpersonationLevel`|El servicio tiene `SeImpersonatePrivilege`|El servicio y el cliente tienen capacidad de delegación|`ImpersonationLevel`|  
|---------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|N/D|Sí|Sí|Delegación|  
|N/D|Sí|No|Suplantación|  
|N/D|No|N/D|Identificación|  
  
## <a name="impersonation-level-obtained-from-s4u-based-impersonation"></a>Nivel de suplantación obtenido de la suplantación basada en S4U  
  
|El servicio tiene `SeTcbPrivilege`|El servicio tiene `SeImpersonatePrivilege`|El servicio y el cliente tienen capacidad de delegación|`ImpersonationLevel`|  
|----------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Sí|Sí|N/D|Suplantación|  
|Sí|No|N/D|Identificación|  
|No|N/D|N/D|Identificación|  
  
## <a name="mapping-a-client-certificate-to-a-windows-account"></a>Asignación de un certificado de cliente a una cuenta de Windows  
 Un cliente se puede autenticar en un servicio mediante un certificado y hacer que el servicio asigne el cliente a una cuenta existente a través de Active Directory. En el XML siguiente, se muestra cómo configurar el servicio para asignar el certificado.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="MapToWindowsAccount">  
      <serviceCredentials>  
        <clientCertificate>  
          <authentication mapClientCertificateToWindowsAccount="true" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 En el código siguiente, se muestra cómo configurar el servicio.  
  
```csharp
// Create a binding that sets a certificate as the client credential type.  
WSHttpBinding b = new WSHttpBinding();  
b.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a service host that maps the certificate to a Windows account.  
Uri httpUri = new Uri("http://localhost/Calculator");  
ServiceHost sh = new ServiceHost(typeof(HelloService), httpUri);  
sh.Credentials.ClientCertificate.Authentication.MapClientCertificateToWindowsAccount = true;  
```  
  
## <a name="delegation"></a>Delegación  
 Para delegar en un servicio back-end, un servicio debe realizar la multibifurcación Kerberos (SSPI sin reserva NTLM), o la autenticación directa de Kerberos en un servicio back-end que utilice la identidad de Windows del cliente. Para delegar en un servicio back-end, cree una clase <xref:System.ServiceModel.ChannelFactory%601> y un canal, y después establezca la comunicación a través del canal al tiempo que suplanta al cliente. Con este tipo de delegación, la distancia a la que puede ubicarse el servicio back-end del servicio front-end depende del nivel de suplantación logrado por éste último. Cuando el nivel de suplantación es <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, los servicios front-end y back-end deben ejecutarse en el mismo equipo. Cuando el nivel de suplantación es <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, los servicios front-end y back-end pueden ejecutarse en equipos distintos o en el mismo equipo. Para habilitar la suplantación en el nivel de delegación es necesario configurar la directiva de dominio de Windows de modo que permita la delegación. Para obtener más información sobre la configuración de Active Directory para admitir la delegación, consulte [Enabling Delegated Authentication (Habilitar la autenticación delegada)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc780217(v=ws.10)).  
  
> [!NOTE]
> Cuando un cliente se autentica en el servicio front-end mediante un nombre de usuario y una contraseña que se corresponden con una cuenta de Windows del servicio back-end, el servicio front-end puede autenticarse en el servicio back-end volviendo a utilizar el nombre de usuario y la contraseña del cliente. Este es un modo especialmente eficaz de flujo de identidad ya que pasar el nombre de usuario y la contraseña al servicio back-end permite a este último realizar la suplantación, pero no constituye una delegación ya que no se usa Kerberos. Active Directory controla la delegación pero no aplica la autenticación del nombre de usuario y la contraseña.  
  
### <a name="delegation-ability-as-a-function-of-impersonation-level"></a>Capacidad de delegación como función del nivel de suplantación  
  
|Nivel de suplantación|El servicio puede realizar una delegación entre procesos|El servicio puede realizar una delegación entre equipos|  
|-------------------------|---------------------------------------------------|---------------------------------------------------|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Identification>|No|Sin|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>|Sí|No|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Delegation>|Sí|Sí|  
  
 En el siguiente ejemplo de código se muestra cómo utilizar la delegación.  
  
 [!code-csharp[c_delegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_delegation/cs/source.cs#1)]
 [!code-vb[c_delegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_delegation/vb/source.vb#1)]  
  
### <a name="how-to-configure-an-application-to-use-constrained-delegation"></a>Cómo: Configurar una aplicación para utilizar la delegación restringida  
 Antes de poder utilizar la delegación restringida, debe configurarse el emisor, el receptor y el controlador de dominio para poder utilizarla. La siguiente lista de procedimiento enumera los pasos para habilitar la delegación restringida. Para obtener más información sobre las diferencias entre la delegación y la delegación restringida, consulte la parte de [Windows Server 2003 Kerberos Extensions (Extensiones Kerberos de Windows Server 2003)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc738207(v=ws.10)) en la que se explica la delegación restringida.  
  
1. En el controlador de dominio, desactive la casilla **La cuenta es importante y no se puede delegar** de la cuenta con la que se está ejecutando la aplicación cliente.  
  
2. En el controlador de dominio, active la casilla **La cuenta es de confianza para la delegación** para la cuenta con la que se está ejecutando la aplicación cliente.  
  
3. En el controlador de domino, configure el equipo de nivel medio de modo que sea de confianza para la delegación haciendo clic en la opción **Equipo de confianza para la delegación** .  
  
4. En el controlador de domino, configure el equipo de nivel medio para utilizar la delegación restringida haciendo clic en la opción **Confiar en este equipo solo para delegación en servicios especificados** .  
  
 Para obtener instrucciones más detalladas sobre la configuración de la delegación restringida, consulte [transición del protocolo Kerberos y delegación restringida](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc739587(v=ws.10)).
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>
- <xref:System.ServiceModel.ImpersonationOption>
- <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>
- <xref:System.ServiceModel.ServiceSecurityContext>
- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- <xref:System.ServiceModel.ChannelFactory%601>
- <xref:System.Security.Principal.TokenImpersonationLevel.Identification>
- [Utilización de la suplantación con la seguridad de transporte](using-impersonation-with-transport-security.md)
- [Suplantar el cliente](../samples/impersonating-the-client.md)
- [Procedimiento para suplantar a un cliente en un servicio](../how-to-impersonate-a-client-on-a-service.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)

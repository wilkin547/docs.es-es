---
title: 'Cómo: Utilizar el proveedor de pertenencia de ASP.NET'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19fb83d21c77f3206c314a2e6c40562fcb75f151
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Cómo: Utilizar el proveedor de pertenencia de ASP.NET
El proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es una característica que permite a los programadores de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios web que permiten a los usuarios crear combinaciones únicas de nombre de usuario y contraseña. Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.  
  
 Para una aplicación de ejemplo, vea [proveedor de pertenencia y rol](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener información sobre el uso de la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] característica de proveedor de roles, consulte [Cómo: utilizar el proveedor de funciones de ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario. La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.  
  
 Los programadores de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden aprovechar de estas características con fines de aumento de la seguridad. Cuando se integran en una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los usuarios deben proporcionar una combinación de nombre de usuario y contraseña a la aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Para transferir los datos a la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio, utilice un enlace que admita las credenciales de nombre y contraseña de usuario, como el <xref:System.ServiceModel.WSHttpBinding> (en la configuración, la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) y establezca la credencial del cliente Escriba a `UserName`. En el servicio, la seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autentica al usuario en función del nombre de usuario y contraseña y también asigna la función especificada por la función [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario/contraseña u otra información de usuario.  
  
### <a name="to-configure-the-membership-provider"></a>Para configurar el proveedor de pertenencia  
  
1.  En el archivo Web.config, en el <`system.web`> elemento, crear una <`membership`> elemento.  
  
2.  Bajo el elemento `<membership>`, cree un elemento `<providers>`.  
  
3.  Como elemento secundario de la <`providers`> elemento, agregue un `<clear />` elemento para vaciar la colección de proveedores.  
  
4.  En el `<clear />` elemento, crear una <`add`> elemento con los siguientes atributos se establece en valores adecuados: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, y `passwordFormat`. El atributo `name` se utiliza más adelante como un valor en el archivo de configuración. El siguiente ejemplo lo define en `SqlMembershipProvider`.  
  
     En el ejemplo siguiente se muestra la sección de configuración.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>Para configurar la seguridad de servicio con el fin de que acepte la combinación de nombre de usuario y contraseña  
  
1.  En el archivo de configuración, en la [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
2.  Agregar un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces. Para obtener más información acerca de cómo crear un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enlace elemento, vea [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Establezca el atributo `mode` del elemento `<security>` en `Message`:  
  
4.  Establecer el `clientCredentialType` atributo de la <`message`> elemento `UserName`. Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.  
  
     El siguiente ejemplo muestra el código de configuración para el enlace.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a>Para configurar un servicio para que utilice el proveedor de pertenencia  
  
1.  Como elemento secundario de la `<system.serviceModel>` elemento, agregue un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento  
  
2.  Agregar un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la <`behaviors`> elemento.  
  
3.  Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` de atributo en un valor adecuado.  
  
4.  Agregar un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) a la <`behavior`> elemento.  
  
5.  Agregar un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) a la `<serviceCredentials>` elemento.  
  
6.  Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Si no se establece el valor `userNamePasswordValidationMode`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la autenticación de Windows en lugar del proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
7.  Establezca el atributo `membershipProviderName` en el nombre del proveedor (especificado al agregar el proveedor en el primer procedimiento de este tema). El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código muestra la configuración para un servicio que utiliza la característica de pertenencia de ASP.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso del proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

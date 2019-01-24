---
title: Procedimiento Usar el proveedor de pertenencia ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 4653a4b4ae90f391eac559210deb611e2a83d0f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634511"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedimiento Usar el proveedor de pertenencia ASP.NET
El proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es una característica que permite a los programadores de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios web que permiten a los usuarios crear combinaciones únicas de nombre de usuario y contraseña. Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.  
  
 Para una aplicación de ejemplo, vea [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener información sobre el uso de la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] característica de proveedor de roles, consulte [Cómo: Usar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario. La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.  
  
 Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovecharse de estas características por motivos de seguridad. Cuando se integra en una aplicación de WCF, los usuarios deben proporcionar una combinación de nombre y contraseña de usuario a la aplicación de cliente WCF. Para transferir los datos al servicio WCF, utilice un enlace que admita las credenciales de nombre y contraseña de usuario, como el <xref:System.ServiceModel.WSHttpBinding> (en configuración, el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) y establezca el cliente de tipo de credencial para `UserName`. En el servicio, la seguridad de WCF autentica al usuario según el nombre de usuario y la contraseña y también asigna el rol especificado por el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] rol.  
  
> [!NOTE]
>  WCF no proporciona métodos para rellenar la base de datos con combinaciones de nombre/contraseña de usuario u otra información de usuario.  
  
### <a name="to-configure-the-membership-provider"></a>Para configurar el proveedor de pertenencia  
  
1.  En el archivo Web.config, bajo el <`system.web`> elemento, cree un <`membership`> elemento.  
  
2.  Bajo el elemento `<membership>`, cree un elemento `<providers>`.  
  
3.  Como elemento secundario de la <`providers`> elemento, agregue un `<clear />` elemento para vaciar la colección de proveedores.  
  
4.  En el `<clear />` elemento, cree un <`add`> elemento con los siguientes atributos se establecen en los valores adecuados: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, y `passwordFormat`. El atributo `name` se utiliza más adelante como un valor en el archivo de configuración. El siguiente ejemplo lo define en `SqlMembershipProvider`.  
  
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
  
1.  En el archivo de configuración en el [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
2.  Agregar un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces. Para obtener más información acerca de cómo crear un elemento de enlace de WCF, vea [Cómo: Especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Establezca el atributo `mode` del elemento `<security>` en `Message`:  
  
4.  Establecer el `clientCredentialType` atributo de la <`message`> elemento para `UserName`. Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.  
  
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
  
3.  Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` atributo en un valor adecuado.  
  
4.  Agregar un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) a la <`behavior`> elemento.  
  
5.  Agregar un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) a la `<serviceCredentials>` elemento.  
  
6.  Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Si el `userNamePasswordValidationMode` valor no está establecido, WCF usa la autenticación de Windows en lugar de la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proveedor de pertenencia.  
  
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
- [Cómo: Usar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

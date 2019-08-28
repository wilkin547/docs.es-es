---
title: Procedimiento para usar el proveedor de pertenencia de ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: b86287440b2265349b853265f12a2f6e48b4cff3
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045273"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedimiento para usar el proveedor de pertenencia de ASP.NET

El proveedor de pertenencia a ASP.NET es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear combinaciones de nombre de usuario y contraseña únicas. Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.

Para obtener una aplicación de ejemplo, vea [pertenencia y proveedor de roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener información acerca del uso de la característica de proveedor [de funciones ASP.net, consulte Cómo: Usar el proveedor de roles ASP.NET con un](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)servicio.

La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario. La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.

Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad. Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario/contraseña para la aplicación cliente de WCF. Para transferir los datos al servicio WCF, use un enlace que admita las credenciales de nombre de usuario/contraseña, <xref:System.ServiceModel.WSHttpBinding> como (en la configuración, el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) y establezca el tipo de `UserName`credencial de cliente en. En el servicio, la seguridad de WCF autentica al usuario basándose en el nombre de usuario y la contraseña, y también asigna el rol especificado por el rol ASP.NET.

> [!NOTE]
> WCF no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario/contraseña u otra información de usuario.

### <a name="to-configure-the-membership-provider"></a>Para configurar el proveedor de pertenencia

1. En el archivo Web. config, en el elemento`system.web`< >, cree un elemento`membership`de > de <.

2. Bajo el elemento `<membership>`, cree un elemento `<providers>`.

3. Como elemento secundario del elemento <`providers`>, agregue un `<clear />` elemento para vaciar la colección de proveedores.

4. En el `<clear />` elemento, cree un <`add`> elemento con los siguientes atributos establecidos en los valores adecuados `name`: `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , , `requiresUniqueEmail`y .`passwordFormat` El atributo `name` se utiliza más adelante como un valor en el archivo de configuración. El siguiente ejemplo lo define en `SqlMembershipProvider`.

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

1. En el archivo de configuración, en el [ \<elemento System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , agregue un [ \<elemento bindings >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) .

2. Agregue un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces. Para obtener más información sobre cómo crear un elemento de enlace [de WCF, consulte Cómo: Especifique un enlace de servicio en](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)la configuración.

3. Establezca el atributo `mode` del elemento `<security>` en `Message`:

4. Establezca el `clientCredentialType` atributo del elemento <`message`> en `UserName`. Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.

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

1. Como elemento secundario del `<system.serviceModel>` elemento, agregue un [ \<elemento Behaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento

2. Agregue un [ \<> serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento >`behaviors`<.

3. Agregue un [ \<> de comportamiento](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca `name` el atributo en un valor adecuado.

4. Agregue un [ \<> serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) al elemento >`behavior`<.

5. Agregue [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) un`<serviceCredentials>` > userNameAuthentication al elemento.

6. Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.

    > [!IMPORTANT]
    > Si no `userNamePasswordValidationMode` se establece el valor, WCF utiliza la autenticación de Windows en lugar del proveedor de pertenencia de ASP.net.

7. Establezca el atributo `membershipProviderName` en el nombre del proveedor (especificado al agregar el proveedor en el primer procedimiento de este tema). El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.

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

- [Procedimientos: Usar el proveedor de roles ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

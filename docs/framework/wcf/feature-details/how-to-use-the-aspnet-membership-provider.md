---
title: Procedimiento para usar el proveedor de pertenencia de ASP.NET
description: Obtenga información sobre cómo el proveedor de pertenencia de ASP.NET admite sitios web que permiten a los usuarios crear un nombre de usuario y una contraseña para el acceso sin tener una cuenta de dominio de Windows.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 6d527993dcf1fc5d5cd39bf22c3e772baf60e62f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246732"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Procedimiento para usar el proveedor de pertenencia de ASP.NET

El proveedor de pertenencia a ASP.NET es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear combinaciones de nombre de usuario y contraseña únicas. Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.

Para obtener una aplicación de ejemplo, vea [pertenencia y proveedor de roles](../samples/membership-and-role-provider.md). Para obtener información sobre el uso de la característica de proveedor de roles ASP.NET, consulte [Cómo: usar el proveedor de roles ASP.net con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md).

La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario. La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.

Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad. Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario/contraseña para la aplicación cliente de WCF. Para transferir los datos al servicio WCF, use un enlace que admita credenciales de nombre de usuario/contraseña, como <xref:System.ServiceModel.WSHttpBinding> (en la configuración, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ) y establezca el tipo de credencial de cliente en `UserName` . En el servicio, la seguridad de WCF autentica al usuario basándose en el nombre de usuario y la contraseña, y también asigna el rol especificado por el rol ASP.NET.

> [!NOTE]
> WCF no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario/contraseña u otra información de usuario.

### <a name="to-configure-the-membership-provider"></a>Para configurar el proveedor de pertenencia

1. En el archivo de Web.config, en el `system.web` elemento> <, cree un `membership` elemento <>.

2. Bajo el elemento `<membership>`, cree un elemento `<providers>`.

3. Como elemento secundario del elemento <`providers`>, agregue un `<clear />` elemento para vaciar la colección de proveedores.

4. En el `<clear />` elemento, cree un <`add`> elemento con los siguientes atributos establecidos en los valores adecuados: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` ,,, `enablePasswordReset` `requiresQuestionAndAnswer` `requiresUniqueEmail` y `passwordFormat` . El atributo `name` se utiliza más adelante como un valor en el archivo de configuración. El siguiente ejemplo lo define en `SqlMembershipProvider`.

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

1. En el archivo de configuración, en el [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.

2. Agregue un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces. Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).

3. Establezca el atributo `mode` del elemento `<security>` en `Message`:

4. Establezca el `clientCredentialType` atributo del elemento <`message`> en `UserName` . Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.

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

1. Como elemento secundario del `<system.serviceModel>` elemento, agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.

2. Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.

3. Agregue [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` atributo en un valor adecuado.

4. Agregue un [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) al elemento <`behavior`>.

5. Agregue un [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) al `<serviceCredentials>` elemento.

6. Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.

    > [!IMPORTANT]
    > Si `userNamePasswordValidationMode` no se establece el valor, WCF utiliza la autenticación de Windows en lugar del proveedor de pertenencia de ASP.net.

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

- [Procedimiento para usar el proveedor de roles ASP.NET con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Proveedor de pertenencia y roles](../samples/membership-and-role-provider.md)

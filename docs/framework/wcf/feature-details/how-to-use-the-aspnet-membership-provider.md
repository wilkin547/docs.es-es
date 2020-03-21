---
title: 'Cómo: Utilizar el proveedor de pertenencia de ASP.NET'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 5b15d56c7150a8478bc32651538903778e3b877d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184791"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Cómo: Utilizar el proveedor de pertenencia de ASP.NET

El proveedor de pertenencia ASP.NET es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear combinaciones únicas de nombre de usuario y contraseña. Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporciona sus credenciales (la combinación de nombre de usuario y contraseña) puede usar el sitio y sus servicios.

Para obtener una aplicación de ejemplo, vea Proveedor de [pertenencia y rol](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener información sobre el uso de la característica ASP.NET proveedor de roles, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)de roles con un servicio .

La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario. La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.

Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar estas características por motivos de seguridad. Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario y contraseña a la aplicación cliente WCF. Para transferir los datos al servicio WCF, use un enlace que admita credenciales de nombre de usuario y contraseña, como (en <xref:System.ServiceModel.WSHttpBinding> configuración, [ \<el wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) y establezca el tipo de credencial de cliente `UserName`en . En el servicio, la seguridad WCF autentica al usuario en función del nombre de usuario y la contraseña y también asigna el rol especificado por el rol ASP.NET.

> [!NOTE]
> WCF no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario y contraseña u otra información de usuario.

### <a name="to-configure-the-membership-provider"></a>Para configurar el proveedor de pertenencia

1. En el archivo Web.config, `system.web` en el elemento `membership` <>, cree un elemento> <.

2. Bajo el elemento `<membership>`, cree un elemento `<providers>`.

3. Como elemento secundario `providers` del elemento> `<clear />` <, agregue un elemento para vaciar la colección de proveedores.

4. En `<clear />` el elemento, `add` cree un elemento> <con `name` `type`los `connectionStringName` `applicationName`siguientes `enablePasswordRetrieval` `enablePasswordReset`atributos establecidos en los valores adecuados: , , , , , `requiresQuestionAndAnswer`, `requiresUniqueEmail`, , , , y `passwordFormat`. El atributo `name` se utiliza más adelante como un valor en el archivo de configuración. El siguiente ejemplo lo define en `SqlMembershipProvider`.

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

1. En el archivo de configuración, en el [ \<elemento de>system.serviceModel,](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) agregue un [ \<elemento>enlaces.](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)

2. Agregue un [ \<>wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces. Para obtener más información acerca de cómo crear un elemento de enlace WCF, vea [Cómo: especificar un enlace](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)de servicio en la configuración .

3. Establezca el atributo `mode` del elemento `<security>` en `Message`:

4. Establezca `clientCredentialType` el atributo `message` del elemento `UserName`> <en . Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.

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

1. Como elemento secundario `<system.serviceModel>` del elemento, agregue un [ \<comportamiento>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento

2. Agregue un [ \<>serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.

3. Agregue [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un comportamiento>`name` y establezca el atributo en un valor adecuado.

4. Agregue un [ \<>serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) al elemento <`behavior`>.

5. Agregue un [ \<>userNameAuthentication](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) al `<serviceCredentials>` elemento.

6. Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.

    > [!IMPORTANT]
    > Si `userNamePasswordValidationMode` no se establece el valor, WCF usa la autenticación de Windows en lugar del proveedor de pertenencia ASP.NET.

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

## <a name="see-also"></a>Consulte también

- [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)

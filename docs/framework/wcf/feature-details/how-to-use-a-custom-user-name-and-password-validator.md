---
title: Cómo utilizar un nombre de usuario personalizado y un validador de contraseñas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 3d01a29671f42e80fdb7ca45223007aa60273ba9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283253"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Cómo utilizar un nombre de usuario personalizado y un validador de contraseñas

De forma predeterminada, cuando se usa un nombre de usuario y una contraseña para la autenticación, Windows Communication Foundation (WCF) usa Windows para validar el nombre de usuario y la contraseña. Sin embargo, WCF permite esquemas de autenticación de nombre de usuario y contraseña personalizados, también conocidos como *Validadores*. Para incorporar un nombre de usuario personalizado y un validador de contraseña, cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> y, a continuación, configúrela.

Para obtener una aplicación de ejemplo, consulte [validador de contraseña de nombre de usuario](../samples/user-name-password-validator.md).

### <a name="to-create-a-custom-user-name-and-password-validator"></a>Para crear un nombre de usuario personalizado y un validador de contraseñas

1. Cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. Implemente el esquema personalizado de autenticación invalidando el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    No utilice el código en el ejemplo siguiente que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción. Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.

    Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Para configurar un servicio con el fin de utilizar un nombre de usuario personalizado y un validador de contraseñas

1. Configure un enlace que utilice la seguridad de mensaje sobre cualquier transporte o la seguridad del nivel de transporte sobre HTTP(S).

    Al utilizar la seguridad de mensaje, agregue uno de los enlaces proporcionados por el sistema, como un [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o un [>\<customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) que admita la seguridad de mensaje y el tipo de credencial `UserName`.

    Al usar la seguridad de nivel de transporte sobre HTTP (S), agregue el [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md), un\<[NetTcpBinding](../../configure-apps/file-schema/wcf/nettcpbinding.md) > o un\<[customBinding](../../configure-apps/file-schema/wcf/custombinding.md) > que utiliza http (S) y el esquema de autenticación `Basic`.

    > [!NOTE]
    > Al usar .NET Framework 3,5 o versiones posteriores, puede usar un validador de nombre de usuario y contraseña personalizados con seguridad de mensaje y transporte. Con WinFX, un validador de nombre de usuario y contraseña personalizados solo se puede usar con la seguridad de mensajes.

    > [!TIP]
    > Para obtener más información sobre el uso de \<netTcpBinding > en este contexto, vea [\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).

    1. En el archivo de configuración, en el elemento [\<System. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) , agregue un elemento [\<bindings >](../../configure-apps/file-schema/wcf/bindings.md) .

    2. Agregue un [\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<elemento > basicHttpBinding](../../configure-apps/file-schema/wcf/basichttpbinding.md) a la sección de enlaces. Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).

    3. Establezca el atributo `mode` del [> de seguridad\<](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<> de seguridad](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) en `Message`, `Transport`o `TransportWithMessageCredential`.

    4. Establezca el atributo `clientCredentialType` del [mensaje de\<>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<> de transporte](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).

        Al utilizar la seguridad de mensaje, establezca el atributo `clientCredentialType` del [mensaje de\<>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) en `UserName`.

        Al utilizar la seguridad de nivel de transporte sobre HTTP (S), establezca el atributo `clientCredentialType` del [> de transporte de\<](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o > de transporte de [\<](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) en `Basic`.

        > [!NOTE]
        > Cuando un servicio WCF se hospeda en Internet Information Services (IIS) mediante la seguridad de nivel de transporte y la propiedad <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> está establecida en <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows. Esto se debe a que, en este escenario, IIS realiza la autenticación de Windows antes de que WCF invoque al autenticador personalizado.

    Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).

    En el ejemplo siguiente se muestra el código de configuración para el enlace:

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. Configure un comportamiento que especifique que un nombre de usuario personalizado y el validador de contraseñas se utilizan para validar los pares de nombre de usuario y para los tokens de seguridad <xref:System.IdentityModel.Tokens.UserNameSecurityToken> entrantes.

    1. Como elemento secundario del elemento [\<System. serviceModel >](../../configure-apps/file-schema/wcf/system-servicemodel.md) , agregue un elemento [\<Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    2. Agregue un [\<serviceBehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento [\<Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) .

    3. Agregue un elemento [\<behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) y establezca el atributo `name` en un valor adecuado.

    4. Agregue un [> de\<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) al elemento [\<Behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .

    5. Agregue un [\<userNameAuthentication >](../../configure-apps/file-schema/wcf/usernameauthentication.md) al [> de\<serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md).

    6. Establezca `userNamePasswordValidationMode` en `Custom`.

        > [!IMPORTANT]
        > Si no se establece el valor de `userNamePasswordValidationMode`, WCF usa la autenticación de Windows en lugar del nombre de usuario personalizado y el validador de contraseñas.

    7. Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.

    En el ejemplo siguiente se muestra el fragmento de `<serviceCredentials>` hasta este punto:

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra cómo crear un nombre de usuario personalizado y el validador de la contraseña. No utilice el código que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción. Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Uso del proveedor de pertenencia de ASP.NET](how-to-use-the-aspnet-membership-provider.md)
- [Autenticación](authentication-in-wcf.md)

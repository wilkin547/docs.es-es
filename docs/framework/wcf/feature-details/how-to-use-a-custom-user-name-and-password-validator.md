---
title: Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas
description: Obtenga información sobre cómo incorporar un validador de contraseñas personalizado para aplicaciones WFC en lugar del nombre de usuario y la validación de contraseña predeterminados de Windows.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7f69db7bf8248593b64cdae4378983c2460de597
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246797"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas

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

    Al utilizar la seguridad de mensaje, agregue uno de los enlaces proporcionados por el sistema, como [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , o un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) que admita la seguridad de mensaje y el `UserName` tipo de credencial.

    Al utilizar la seguridad de nivel de transporte sobre HTTP (S), agregue [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) , un [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) o un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) que use http (s) y el `Basic` esquema de autenticación.

    > [!NOTE]
    > Al usar .NET Framework 3,5 o versiones posteriores, puede usar un validador de nombre de usuario y contraseña personalizados con seguridad de mensaje y transporte. Con WinFX, un validador de nombre de usuario y contraseña personalizados solo se puede usar con la seguridad de mensajes.

    > [!TIP]
    > Para obtener más información sobre \<netTcpBinding> el uso de en este contexto, vea [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .

    1. En el archivo de configuración, en el [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.

    2. Agregue un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) elemento o a la sección de enlaces. Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).

    3. Establezca el `mode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) en `Message` , `Transport` o `TransportWithMessageCredential` .

    4. Establezca el `clientCredentialType` atributo de [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .

        Al utilizar la seguridad de mensaje, establezca el `clientCredentialType` atributo de [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) en `UserName` .

        Al utilizar la seguridad de nivel de transporte sobre HTTP (S), establezca el `clientCredentialType` atributo de [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) en `Basic` .

        > [!NOTE]
        > Cuando un servicio WCF se hospeda en Internet Information Services (IIS) mediante la seguridad de nivel de transporte y la <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> propiedad se establece en <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> , el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows. Esto se debe a que, en este escenario, IIS realiza la autenticación de Windows antes de que WCF invoque al autenticador personalizado.

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

    1. Como elemento secundario del [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.

    2. Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.

    3. Agregue un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento y establezca el `name` atributo en un valor adecuado.

    4. Agregue un [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) al [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.

    5. Agregue [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .

    6. Establecer `userNamePasswordValidationMode` en `Custom`.

        > [!IMPORTANT]
        > Si `userNamePasswordValidationMode` no se establece el valor, WCF usa la autenticación de Windows en lugar del nombre de usuario personalizado y el validador de contraseñas.

    7. Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.

    En el siguiente ejemplo se muestra el `<serviceCredentials>` fragmento hasta este punto:

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
- [Procedimiento para usar el proveedor de pertenencia de ASP.NET](how-to-use-the-aspnet-membership-provider.md)
- [Autenticación](authentication-in-wcf.md)

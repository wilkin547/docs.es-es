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
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="1d325-103">Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1d325-103">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="1d325-104">De forma predeterminada, cuando se usa un nombre de usuario y una contraseña para la autenticación, Windows Communication Foundation (WCF) usa Windows para validar el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="1d325-104">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="1d325-105">Sin embargo, WCF permite esquemas de autenticación de nombre de usuario y contraseña personalizados, también conocidos como *Validadores*.</span><span class="sxs-lookup"><span data-stu-id="1d325-105">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="1d325-106">Para incorporar un nombre de usuario personalizado y un validador de contraseña, cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> y, a continuación, configúrela.</span><span class="sxs-lookup"><span data-stu-id="1d325-106">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="1d325-107">Para obtener una aplicación de ejemplo, consulte [validador de contraseña de nombre de usuario](../samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="1d325-107">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="1d325-108">Para crear un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1d325-108">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="1d325-109">Cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="1d325-109">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="1d325-110">Implemente el esquema personalizado de autenticación invalidando el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d325-110">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="1d325-111">No utilice el código en el ejemplo siguiente que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="1d325-111">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="1d325-112">Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d325-112">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="1d325-113">Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d325-113">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="1d325-114">Para configurar un servicio con el fin de utilizar un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="1d325-114">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="1d325-115">Configure un enlace que utilice la seguridad de mensaje sobre cualquier transporte o la seguridad del nivel de transporte sobre HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="1d325-115">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="1d325-116">Al utilizar la seguridad de mensaje, agregue uno de los enlaces proporcionados por el sistema, como [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , o un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) que admita la seguridad de mensaje y el `UserName` tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="1d325-116">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="1d325-117">Al utilizar la seguridad de nivel de transporte sobre HTTP (S), agregue [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) , un [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) o un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) que use http (s) y el `Basic` esquema de autenticación.</span><span class="sxs-lookup"><span data-stu-id="1d325-117">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d325-118">Al usar .NET Framework 3,5 o versiones posteriores, puede usar un validador de nombre de usuario y contraseña personalizados con seguridad de mensaje y transporte.</span><span class="sxs-lookup"><span data-stu-id="1d325-118">When using .NET Framework 3.5 or later versions, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="1d325-119">Con WinFX, un validador de nombre de usuario y contraseña personalizados solo se puede usar con la seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1d325-119">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="1d325-120">Para obtener más información sobre \<netTcpBinding> el uso de en este contexto, vea [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1d325-120">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="1d325-121">En el archivo de configuración, en el [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1d325-121">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="1d325-122">Agregue un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) elemento o a la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="1d325-122">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="1d325-123">Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1d325-123">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="1d325-124">Establezca el `mode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) en `Message` , `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="1d325-124">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="1d325-125">Establezca el `clientCredentialType` atributo de [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1d325-125">Set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="1d325-126">Al utilizar la seguridad de mensaje, establezca el `clientCredentialType` atributo de [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) en `UserName` .</span><span class="sxs-lookup"><span data-stu-id="1d325-126">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="1d325-127">Al utilizar la seguridad de nivel de transporte sobre HTTP (S), establezca el `clientCredentialType` atributo de [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) en `Basic` .</span><span class="sxs-lookup"><span data-stu-id="1d325-127">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1d325-128">Cuando un servicio WCF se hospeda en Internet Information Services (IIS) mediante la seguridad de nivel de transporte y la <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> propiedad se establece en <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> , el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1d325-128">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="1d325-129">Esto se debe a que, en este escenario, IIS realiza la autenticación de Windows antes de que WCF invoque al autenticador personalizado.</span><span class="sxs-lookup"><span data-stu-id="1d325-129">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="1d325-130">Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1d325-130">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="1d325-131">En el ejemplo siguiente se muestra el código de configuración para el enlace:</span><span class="sxs-lookup"><span data-stu-id="1d325-131">The following example shows the configuration code for the binding:</span></span>

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

2. <span data-ttu-id="1d325-132">Configure un comportamiento que especifique que un nombre de usuario personalizado y el validador de contraseñas se utilizan para validar los pares de nombre de usuario y para los tokens de seguridad <xref:System.IdentityModel.Tokens.UserNameSecurityToken> entrantes.</span><span class="sxs-lookup"><span data-stu-id="1d325-132">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="1d325-133">Como elemento secundario del [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1d325-133">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="1d325-134">Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1d325-134">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="1d325-135">Agregue un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="1d325-135">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="1d325-136">Agregue un [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) al [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1d325-136">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="1d325-137">Agregue [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="1d325-137">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="1d325-138">Establecer `userNamePasswordValidationMode` en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1d325-138">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="1d325-139">Si `userNamePasswordValidationMode` no se establece el valor, WCF usa la autenticación de Windows en lugar del nombre de usuario personalizado y el validador de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1d325-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="1d325-140">Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="1d325-140">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="1d325-141">En el siguiente ejemplo se muestra el `<serviceCredentials>` fragmento hasta este punto:</span><span class="sxs-lookup"><span data-stu-id="1d325-141">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="1d325-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d325-142">Example</span></span>

<span data-ttu-id="1d325-143">El ejemplo de código siguiente muestra cómo crear un nombre de usuario personalizado y el validador de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="1d325-143">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="1d325-144">No utilice el código que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="1d325-144">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="1d325-145">Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d325-145">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="1d325-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d325-146">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="1d325-147">Procedimiento para usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1d325-147">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="1d325-148">Autenticación</span><span class="sxs-lookup"><span data-stu-id="1d325-148">Authentication</span></span>](authentication-in-wcf.md)

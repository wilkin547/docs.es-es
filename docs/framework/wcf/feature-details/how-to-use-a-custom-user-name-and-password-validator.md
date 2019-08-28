---
title: Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7df6ec57204990066ce59700e5c2582701f2a81a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045912"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="2fe6c-102">Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2fe6c-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="2fe6c-103">De forma predeterminada, cuando se usa un nombre de usuario y una contraseña para la autenticación, Windows Communication Foundation (WCF) usa Windows para validar el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="2fe6c-104">Sin embargo, WCF permite esquemas de autenticación de nombre de usuario y contraseña personalizados, también conocidos como validadores.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="2fe6c-105">Para incorporar un nombre de usuario personalizado y un validador de contraseña, cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> y, a continuación, configúrela.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="2fe6c-106">Para obtener una aplicación de ejemplo, consulte validador de [contraseña de nombre de usuario](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6c-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="2fe6c-107">Para crear un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2fe6c-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="2fe6c-108">Cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="2fe6c-109">Implemente el esquema personalizado de autenticación invalidando el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="2fe6c-110">No utilice el código en el ejemplo siguiente que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="2fe6c-111">Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="2fe6c-112">Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="2fe6c-113">Para configurar un servicio con el fin de utilizar un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="2fe6c-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="2fe6c-114">Configure un enlace que utilice la seguridad de mensaje sobre cualquier transporte o la seguridad del nivel de transporte sobre HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="2fe6c-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="2fe6c-115">Al utilizar la seguridad de mensaje, agregue uno de los enlaces proporcionados por el sistema, como un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)o un [ \<> customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) que admita la seguridad de `UserName` mensaje y el tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="2fe6c-116">Al utilizar la seguridad de nivel de transporte sobre http (S), agregue el [ \<> wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), un [ \<> netTcpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o un [ \<customBinding > ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)que usa http (S) y el `Basic` esquema de autenticación.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fe6c-117">Si se utiliza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o una versión posterior, puede usarse un validador de nombre de usuario y de contraseña personalizado con la seguridad de mensaje y de transporte.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="2fe6c-118">Con WinFX, un validador de nombre de usuario y contraseña personalizados solo se puede usar con la seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="2fe6c-119">Para obtener más información sobre \<el uso de la > netTcpBinding en este contexto, vea [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2fe6c-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>

    1. <span data-ttu-id="2fe6c-120">En el archivo de configuración, en el [ \<elemento System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , agregue un [ \<elemento bindings >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="2fe6c-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="2fe6c-121">Agregue un [ \<elemento wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) a la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="2fe6c-122">Para obtener más información sobre cómo crear un elemento de enlace [de WCF, consulte Cómo: Especifique un enlace de servicio en](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)la configuración.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="2fe6c-123">Establezca el `mode` atributo del [ \<> de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [ \<el > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) en `Message`, `TransportWithMessageCredential` `Transport`o.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="2fe6c-124">Establezca el `clientCredentialType` atributo [ \<del > de mensajes](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [ \<del > de transporte](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6c-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="2fe6c-125">Al utilizar la seguridad `clientCredentialType` `UserName` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) de mensaje, establezca el atributo del mensaje > en.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="2fe6c-126">Al utilizar la seguridad de nivel de transporte sobre http (S), `clientCredentialType` establezca el atributo [ \<del > de transporte](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [ \<transporte >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) en. `Basic`</span><span class="sxs-lookup"><span data-stu-id="2fe6c-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2fe6c-127">Cuando un servicio WCF se hospeda en Internet Information Services (IIS) mediante la seguridad de nivel de transporte <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> y la propiedad se <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>establece en, el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="2fe6c-128">Esto se debe a que, en este escenario, IIS realiza la autenticación de Windows antes de que WCF invoque al autenticador personalizado.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="2fe6c-129">Para obtener más información sobre cómo crear un elemento de enlace [de WCF, consulte Cómo: Especifique un enlace de servicio en](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)la configuración.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="2fe6c-130">El siguiente ejemplo muestra el código de configuración para el enlace.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-130">The following example shows the configuration code for the binding.</span></span>

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

2. <span data-ttu-id="2fe6c-131">Configure un comportamiento que especifique que un nombre de usuario personalizado y el validador de contraseñas se utilizan para validar los pares de nombre de usuario y para los tokens de seguridad <xref:System.IdentityModel.Tokens.UserNameSecurityToken> entrantes.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="2fe6c-132">Como elemento secundario [ \<del elemento System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , agregue un [ \<elemento Behaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="2fe6c-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="2fe6c-133">Agregue un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) [ >serviceBehaviorsalelementoBehaviors>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2fe6c-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="2fe6c-134">Agregue un elemento de [ \<> de comportamiento](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) y `name` establezca el atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="2fe6c-135">Agregue un [ \<> serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) al elemento [ \<> de comportamiento](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="2fe6c-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="2fe6c-136">Agregue un [ \<> userNameAuthentication](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) a la [ \<> serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6c-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="2fe6c-137">Establezca `userNamePasswordValidationMode` en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="2fe6c-138">Si no `userNamePasswordValidationMode` se establece el valor, WCF usa la autenticación de Windows en lugar del nombre de usuario personalizado y el validador de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="2fe6c-139">Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="2fe6c-140">El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="2fe6c-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2fe6c-141">Example</span></span>

<span data-ttu-id="2fe6c-142">El ejemplo de código siguiente muestra cómo crear un nombre de usuario personalizado y el validador de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="2fe6c-143">No utilice el código que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="2fe6c-144">Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe6c-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="2fe6c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fe6c-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="2fe6c-146">Procedimientos: Usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2fe6c-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="2fe6c-147">Autenticación</span><span class="sxs-lookup"><span data-stu-id="2fe6c-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)

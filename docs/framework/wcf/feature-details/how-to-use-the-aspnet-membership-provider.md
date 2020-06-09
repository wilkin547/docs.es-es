---
title: Procedimiento para usar el proveedor de pertenencia de ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 840e4a5d365f2adbaf335c1061a580665a39824d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595328"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="13dfa-102">Procedimiento para usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="13dfa-102">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="13dfa-103">El proveedor de pertenencia a ASP.NET es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear combinaciones de nombre de usuario y contraseña únicas.</span><span class="sxs-lookup"><span data-stu-id="13dfa-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="13dfa-104">Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios.</span><span class="sxs-lookup"><span data-stu-id="13dfa-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="13dfa-105">Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="13dfa-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="13dfa-106">En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="13dfa-106">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="13dfa-107">Para obtener una aplicación de ejemplo, vea [pertenencia y proveedor de roles](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="13dfa-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="13dfa-108">Para obtener información sobre el uso de la característica de proveedor de roles ASP.NET, consulte [Cómo: usar el proveedor de roles ASP.net con un servicio](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="13dfa-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="13dfa-109">La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario.</span><span class="sxs-lookup"><span data-stu-id="13dfa-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="13dfa-110">La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.</span><span class="sxs-lookup"><span data-stu-id="13dfa-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="13dfa-111">Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="13dfa-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="13dfa-112">Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario/contraseña para la aplicación cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="13dfa-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="13dfa-113">Para transferir los datos al servicio WCF, use un enlace que admita credenciales de nombre de usuario/contraseña, como <xref:System.ServiceModel.WSHttpBinding> (en la configuración, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ) y establezca el tipo de credencial de cliente en `UserName` .</span><span class="sxs-lookup"><span data-stu-id="13dfa-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="13dfa-114">En el servicio, la seguridad de WCF autentica al usuario basándose en el nombre de usuario y la contraseña, y también asigna el rol especificado por el rol ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="13dfa-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="13dfa-115">WCF no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario/contraseña u otra información de usuario.</span><span class="sxs-lookup"><span data-stu-id="13dfa-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="13dfa-116">Para configurar el proveedor de pertenencia</span><span class="sxs-lookup"><span data-stu-id="13dfa-116">To configure the membership provider</span></span>

1. <span data-ttu-id="13dfa-117">En el archivo Web. config, en el `system.web` elemento < >, cree un elemento de > de < `membership` .</span><span class="sxs-lookup"><span data-stu-id="13dfa-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="13dfa-118">Bajo el elemento `<membership>`, cree un elemento `<providers>`.</span><span class="sxs-lookup"><span data-stu-id="13dfa-118">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="13dfa-119">Como elemento secundario del elemento <`providers`>, agregue un `<clear />` elemento para vaciar la colección de proveedores.</span><span class="sxs-lookup"><span data-stu-id="13dfa-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="13dfa-120">En el `<clear />` elemento, cree un <`add`> elemento con los siguientes atributos establecidos en los valores adecuados: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` ,,, `enablePasswordReset` `requiresQuestionAndAnswer` `requiresUniqueEmail` y `passwordFormat` .</span><span class="sxs-lookup"><span data-stu-id="13dfa-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="13dfa-121">El atributo `name` se utiliza más adelante como un valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="13dfa-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="13dfa-122">El siguiente ejemplo lo define en `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="13dfa-122">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="13dfa-123">En el ejemplo siguiente se muestra la sección de configuración.</span><span class="sxs-lookup"><span data-stu-id="13dfa-123">The following example shows the configuration section.</span></span>

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="13dfa-124">Para configurar la seguridad de servicio con el fin de que acepte la combinación de nombre de usuario y contraseña</span><span class="sxs-lookup"><span data-stu-id="13dfa-124">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="13dfa-125">En el archivo de configuración, en el [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, agregue un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="13dfa-125">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="13dfa-126">Agregue un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="13dfa-126">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="13dfa-127">Para obtener más información sobre cómo crear un elemento de enlace de WCF, vea [Cómo: especificar un enlace de servicio en la configuración](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="13dfa-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="13dfa-128">Establezca el atributo `mode` del elemento `<security>` en `Message`:</span><span class="sxs-lookup"><span data-stu-id="13dfa-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="13dfa-129">Establezca el `clientCredentialType` atributo del elemento <`message`> en `UserName` .</span><span class="sxs-lookup"><span data-stu-id="13dfa-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="13dfa-130">Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="13dfa-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="13dfa-131">El siguiente ejemplo muestra el código de configuración para el enlace.</span><span class="sxs-lookup"><span data-stu-id="13dfa-131">The following example shows the configuration code for the binding.</span></span>

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="13dfa-132">Para configurar un servicio para que utilice el proveedor de pertenencia</span><span class="sxs-lookup"><span data-stu-id="13dfa-132">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="13dfa-133">Como elemento secundario del `<system.serviceModel>` elemento, agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="13dfa-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="13dfa-134">Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.</span><span class="sxs-lookup"><span data-stu-id="13dfa-134">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="13dfa-135">Agregue [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="13dfa-135">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="13dfa-136">Agregue un [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) al elemento <`behavior`>.</span><span class="sxs-lookup"><span data-stu-id="13dfa-136">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="13dfa-137">Agregue un [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) al `<serviceCredentials>` elemento.</span><span class="sxs-lookup"><span data-stu-id="13dfa-137">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="13dfa-138">Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="13dfa-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="13dfa-139">Si `userNamePasswordValidationMode` no se establece el valor, WCF utiliza la autenticación de Windows en lugar del proveedor de pertenencia de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="13dfa-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="13dfa-140">Establezca el atributo `membershipProviderName` en el nombre del proveedor (especificado al agregar el proveedor en el primer procedimiento de este tema).</span><span class="sxs-lookup"><span data-stu-id="13dfa-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="13dfa-141">El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.</span><span class="sxs-lookup"><span data-stu-id="13dfa-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

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

## <a name="example"></a><span data-ttu-id="13dfa-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13dfa-142">Example</span></span>

<span data-ttu-id="13dfa-143">El siguiente código muestra la configuración para un servicio que utiliza la característica de pertenencia de ASP.</span><span class="sxs-lookup"><span data-stu-id="13dfa-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13dfa-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="13dfa-144">See also</span></span>

- [<span data-ttu-id="13dfa-145">Procedimiento para usar el proveedor de roles ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="13dfa-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="13dfa-146">Proveedor de pertenencia y roles</span><span class="sxs-lookup"><span data-stu-id="13dfa-146">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)

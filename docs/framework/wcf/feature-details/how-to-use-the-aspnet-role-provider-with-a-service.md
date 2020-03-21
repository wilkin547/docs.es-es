---
title: 'Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184769"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="6a47a-102">Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="6a47a-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="6a47a-103">El proveedor de roles ASP.NET (junto con el proveedor de pertenencia ASP.NET) es una característica que permite a los desarrolladores de ASP.NET crear sitios Web que permiten a los usuarios crear una cuenta con un sitio y asignar roles con fines de autorización.</span><span class="sxs-lookup"><span data-stu-id="6a47a-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="6a47a-104">Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="6a47a-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="6a47a-105">Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="6a47a-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="6a47a-106">En su lugar, cualquier usuario que proporciona sus credenciales (la combinación de nombre de usuario y contraseña) puede usar el sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="6a47a-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="6a47a-107">Para obtener una aplicación de ejemplo, vea Proveedor de [pertenencia y rol](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="6a47a-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="6a47a-108">Para obtener más información acerca de la característica de proveedor de pertenencia ASP.NET, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)de pertenencia .</span><span class="sxs-lookup"><span data-stu-id="6a47a-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="6a47a-109">La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario.</span><span class="sxs-lookup"><span data-stu-id="6a47a-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="6a47a-110">Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar estas características por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6a47a-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="6a47a-111">Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario y contraseña a la aplicación cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="6a47a-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="6a47a-112">Para permitir que WCF use la base de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> datos, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> debe <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>crear una instancia de la clase, <xref:System.ServiceModel.ServiceHost> establecer su propiedad en y agregar la instancia a la colección de comportamientos a la que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="6a47a-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="6a47a-113">Configurar el proveedor de roles</span><span class="sxs-lookup"><span data-stu-id="6a47a-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="6a47a-114">En el archivo Web.config, `system.web` en el elemento `roleManager`> <, `enabled` agregue `true`un elemento> <y establezca su atributo en .</span><span class="sxs-lookup"><span data-stu-id="6a47a-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="6a47a-115">Defina el atributo `defaultProvider` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="6a47a-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="6a47a-116">Como elemento secundario `roleManager` del elemento <`providers`>, agregue un elemento> <.</span><span class="sxs-lookup"><span data-stu-id="6a47a-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="6a47a-117">Como elemento secundario `providers` del elemento> `add` <, agregue un elemento> `name`de `type` `connectionStringName`<`applicationName`con los siguientes atributos establecidos en los valores adecuados: , , , , , , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a47a-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="6a47a-118">Configure el servicio para que use el proveedor de roles</span><span class="sxs-lookup"><span data-stu-id="6a47a-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="6a47a-119">En el archivo Web.config, agregue un [ \<elemento>system.serviceModel.](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6a47a-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="6a47a-120">Agregue un [ \<elemento>comportamientos](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) al elemento> <. `system.ServiceModel`</span><span class="sxs-lookup"><span data-stu-id="6a47a-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="6a47a-121">Agregue un [ \<>serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.</span><span class="sxs-lookup"><span data-stu-id="6a47a-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="6a47a-122">Agregue [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un comportamiento>`name` elemento y establezca el atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="6a47a-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="6a47a-123">Agregue un [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) al elemento <`behavior`>.</span><span class="sxs-lookup"><span data-stu-id="6a47a-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="6a47a-124">Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="6a47a-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="6a47a-125">Defina el atributo `roleProviderName` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="6a47a-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="6a47a-126">En el ejemplo siguiente se muestra un fragmento de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6a47a-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6a47a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a47a-127">See also</span></span>

- [<span data-ttu-id="6a47a-128">Proveedor de pertenencia y roles</span><span class="sxs-lookup"><span data-stu-id="6a47a-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="6a47a-129">Uso del proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6a47a-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

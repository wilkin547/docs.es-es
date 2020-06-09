---
title: Procedimiento para usar el proveedor de roles ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595302"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="88fef-102">Procedimiento para usar el proveedor de roles ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="88fef-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="88fef-103">El proveedor de roles ASP.NET (junto con el proveedor de pertenencia a ASP.NET) es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear una cuenta con un sitio y asignarles roles para fines de autorización.</span><span class="sxs-lookup"><span data-stu-id="88fef-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="88fef-104">Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="88fef-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="88fef-105">Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="88fef-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="88fef-106">En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario y contraseña) puede utilizar el sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="88fef-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="88fef-107">Para obtener una aplicación de ejemplo, vea [pertenencia y proveedor de roles](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="88fef-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="88fef-108">Para obtener más información acerca de la característica de proveedor de pertenencia de ASP.NET, consulte [Cómo: usar el proveedor de pertenencia a ASP.net](how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="88fef-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="88fef-109">La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario.</span><span class="sxs-lookup"><span data-stu-id="88fef-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="88fef-110">Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="88fef-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="88fef-111">Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario/contraseña para la aplicación cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88fef-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="88fef-112">Para permitir que WCF use la base de datos, debe crear una instancia de la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> clase, establecer su <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> propiedad en <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> y agregar la instancia de a la colección de comportamientos al <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="88fef-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="88fef-113">Configurar el proveedor de roles</span><span class="sxs-lookup"><span data-stu-id="88fef-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="88fef-114">En el archivo Web. config, en el `system.web` elemento < >, agregue un `roleManager` elemento < > y establezca su `enabled` atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="88fef-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="88fef-115">Defina el atributo `defaultProvider` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="88fef-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="88fef-116">Como elemento secundario del elemento <`roleManager`>, agregue un elemento <`providers`>.</span><span class="sxs-lookup"><span data-stu-id="88fef-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="88fef-117">Como elemento secundario del elemento <`providers`>, agregue un elemento <`add`> con los siguientes atributos establecidos en los valores adecuados: `name` , `type` , `connectionStringName` y `applicationName` , tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fef-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="88fef-118">Configurar el servicio para usar el proveedor de roles</span><span class="sxs-lookup"><span data-stu-id="88fef-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="88fef-119">En el archivo Web. config, agregue un [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="88fef-119">In the Web.config file, add a [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="88fef-120">Agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento al elemento <`system.ServiceModel`>.</span><span class="sxs-lookup"><span data-stu-id="88fef-120">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="88fef-121">Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.</span><span class="sxs-lookup"><span data-stu-id="88fef-121">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="88fef-122">Agregue un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="88fef-122">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="88fef-123">Agregue un [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) al elemento <`behavior`>.</span><span class="sxs-lookup"><span data-stu-id="88fef-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="88fef-124">Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="88fef-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="88fef-125">Defina el atributo `roleProviderName` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="88fef-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="88fef-126">En el ejemplo siguiente se muestra un fragmento de la configuración.</span><span class="sxs-lookup"><span data-stu-id="88fef-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88fef-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="88fef-127">See also</span></span>

- [<span data-ttu-id="88fef-128">Proveedor de pertenencia y roles</span><span class="sxs-lookup"><span data-stu-id="88fef-128">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
- [<span data-ttu-id="88fef-129">Procedimiento para usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="88fef-129">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)

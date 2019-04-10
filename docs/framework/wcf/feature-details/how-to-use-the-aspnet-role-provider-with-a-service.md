---
title: Filtrar para usar el proveedor de roles ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 8f3fadc60645ef81d2683c63fda0ddd5bf24c982
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301144"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="2fb8a-102">Filtrar para usar el proveedor de roles ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="2fb8a-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="2fb8a-103">El proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (junto con el proveedor de pertenencia [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ) es una característica que permite a los programadores [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios Web que permitan a los usuarios crear una cuenta con un sitio y asignar funciones para los propósitos de la autorización.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="2fb8a-104">Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="2fb8a-105">Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="2fb8a-106">En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="2fb8a-107">Para una aplicación de ejemplo, vea [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2fb8a-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="2fb8a-108">Para obtener más información sobre la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] característica de proveedor de pertenencia, vea [Cómo: Usar el proveedor de pertenencia a ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2fb8a-108">For more information about the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="2fb8a-109">La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="2fb8a-110">Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovecharse de estas características por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="2fb8a-111">Cuando se integra en una aplicación de WCF, los usuarios deben proporcionar una combinación de nombre y contraseña de usuario a la aplicación de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="2fb8a-112">Para habilitar WCF usar la base de datos, debe crear una instancia de la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> clase, establezca su <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> propiedad a <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>y agregue la instancia a la colección de comportamientos para el <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="2fb8a-113">Para configurar el proveedor de funciones</span><span class="sxs-lookup"><span data-stu-id="2fb8a-113">To configure the role provider</span></span>  
  
1. <span data-ttu-id="2fb8a-114">En el archivo Web.config, bajo el <`system.web`> elemento, agregar un <`roleManager`> y establezca su `enabled` atributo `true`.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="2fb8a-115">Defina el atributo `defaultProvider` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="2fb8a-116">Como elemento secundario de la <`roleManager`> elemento, agregar un <`providers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="2fb8a-117">Como elemento secundario de la <`providers`> elemento, agregar un <`add`> elemento con los siguientes atributos se establecen en los valores adecuados: `name`, `type`, `connectionStringName`, y `applicationName`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="2fb8a-118">Para configurar el servicio para utilizar el proveedor de funciones</span><span class="sxs-lookup"><span data-stu-id="2fb8a-118">To configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="2fb8a-119">En el archivo Web.config, agregue un [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="2fb8a-120">Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento a la <`system.ServiceModel`> elemento.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="2fb8a-121">Agregar un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la <`behaviors`> elemento.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="2fb8a-122">Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="2fb8a-123">Agregar un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) a la <`behavior`> elemento.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="2fb8a-124">Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="2fb8a-125">Defina el atributo `roleProviderName` a `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="2fb8a-126">En el ejemplo siguiente se muestra un fragmento de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2fb8a-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2fb8a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fb8a-127">See also</span></span>

- [<span data-ttu-id="2fb8a-128">Proveedor de pertenencia y roles</span><span class="sxs-lookup"><span data-stu-id="2fb8a-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="2fb8a-129">Filtrar para usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2fb8a-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)

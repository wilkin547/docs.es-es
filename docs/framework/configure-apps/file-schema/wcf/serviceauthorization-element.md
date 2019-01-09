---
title: '&lt;serviceAuthorization&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: 6c69d10eb2f6cdf4546dd5895d196723417f5494
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146009"
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="56705-102">&lt;serviceAuthorization&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="56705-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="56705-103">Especifica valores que autorizan que el acceso repare las operaciones</span><span class="sxs-lookup"><span data-stu-id="56705-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="56705-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="56705-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56705-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="56705-105">\<behaviors></span></span>  
<span data-ttu-id="56705-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="56705-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="56705-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="56705-107">\<behavior></span></span>  
<span data-ttu-id="56705-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="56705-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56705-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56705-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56705-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56705-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56705-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56705-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56705-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="56705-112">Attributes</span></span>  
  
|<span data-ttu-id="56705-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="56705-113">Attribute</span></span>|<span data-ttu-id="56705-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="56705-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56705-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="56705-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="56705-116">Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="56705-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="56705-117">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="56705-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="56705-118">Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="56705-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="56705-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="56705-119">principalPermissionMode</span></span>|<span data-ttu-id="56705-120">Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="56705-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="56705-121">Los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="56705-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="56705-122">-None</span><span class="sxs-lookup"><span data-stu-id="56705-122">-   None</span></span><br /><span data-ttu-id="56705-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="56705-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="56705-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="56705-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="56705-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="56705-125">-   Custom</span></span><br /><br /> <span data-ttu-id="56705-126">El valor predeterminado es UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="56705-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="56705-127">El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="56705-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="56705-128">Para obtener más información sobre el uso de este atributo, vea [Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="56705-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="56705-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="56705-129">roleProviderName</span></span>|<span data-ttu-id="56705-130">Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="56705-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="56705-131">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="56705-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="56705-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="56705-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="56705-133">Una cadena que contiene el tipo de administrador de autorización de servicio.</span><span class="sxs-lookup"><span data-stu-id="56705-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="56705-134">Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="56705-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56705-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56705-135">Child Elements</span></span>  
  
|<span data-ttu-id="56705-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="56705-136">Element</span></span>|<span data-ttu-id="56705-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="56705-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56705-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="56705-138">authorizationPolicies</span></span>|<span data-ttu-id="56705-139">Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="56705-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="56705-140">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="56705-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="56705-141">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="56705-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="56705-142">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="56705-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="56705-143">Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="56705-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56705-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56705-144">Parent Elements</span></span>  
  
|<span data-ttu-id="56705-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="56705-145">Element</span></span>|<span data-ttu-id="56705-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="56705-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56705-147">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="56705-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="56705-148">Contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="56705-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56705-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56705-149">Remarks</span></span>  
 <span data-ttu-id="56705-150">Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="56705-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="56705-151">El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.</span><span class="sxs-lookup"><span data-stu-id="56705-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="56705-152">El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="56705-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="56705-153">También puede especificar `UseAspNetRoles` para usar un proveedor de roles personalizados que se configura bajo el \<system.web > elemento, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="56705-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 <span data-ttu-id="56705-154">El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.</span><span class="sxs-lookup"><span data-stu-id="56705-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="56705-155">Para obtener un ejemplo detallado del uso de este elemento de configuración, consulte [autorizar el acceso a las operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="56705-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56705-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="56705-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="56705-157">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="56705-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="56705-158">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="56705-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="56705-159">Cómo: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="56705-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="56705-160">Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="56705-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [<span data-ttu-id="56705-161">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="56705-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

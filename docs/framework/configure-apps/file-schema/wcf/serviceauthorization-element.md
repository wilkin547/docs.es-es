---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834019"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="d63e8-102">\<elemento > serviceAuthorization</span><span class="sxs-lookup"><span data-stu-id="d63e8-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="d63e8-103">Especifica valores que autorizan que el acceso repare las operaciones</span><span class="sxs-lookup"><span data-stu-id="d63e8-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="d63e8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d63e8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d63e8-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d63e8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d63e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**comportamientos**](behaviors.md)\<></span><span class="sxs-lookup"><span data-stu-id="d63e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d63e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d63e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d63e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**comportamiento**](behavior-of-servicebehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="d63e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d63e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceAuthorization >**</span><span class="sxs-lookup"><span data-stu-id="d63e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d63e8-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d63e8-110">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d63e8-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d63e8-111">Attributes and elements</span></span>

<span data-ttu-id="d63e8-112">En las secciones siguientes se describen los atributos, los elementos secundarios y los elementos primarios:</span><span class="sxs-lookup"><span data-stu-id="d63e8-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="d63e8-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d63e8-113">Attributes</span></span>

|<span data-ttu-id="d63e8-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d63e8-114">Attribute</span></span>|<span data-ttu-id="d63e8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d63e8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d63e8-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="d63e8-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="d63e8-117">Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d63e8-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="d63e8-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d63e8-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="d63e8-119">Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="d63e8-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="d63e8-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="d63e8-120">principalPermissionMode</span></span>|<span data-ttu-id="d63e8-121">Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d63e8-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="d63e8-122">Los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d63e8-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="d63e8-123">-Ninguno</span><span class="sxs-lookup"><span data-stu-id="d63e8-123">-   None</span></span><br /><span data-ttu-id="d63e8-124">-   UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="d63e8-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="d63e8-125">-   UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="d63e8-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="d63e8-126">-Personalizado</span><span class="sxs-lookup"><span data-stu-id="d63e8-126">-   Custom</span></span><br /><br /> <span data-ttu-id="d63e8-127">El valor predeterminado es UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="d63e8-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="d63e8-128">El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="d63e8-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="d63e8-129">Para obtener más información sobre el uso de este atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="d63e8-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="d63e8-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="d63e8-130">roleProviderName</span></span>|<span data-ttu-id="d63e8-131">Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d63e8-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d63e8-132">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d63e8-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="d63e8-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="d63e8-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="d63e8-134">Una cadena que contiene el tipo de administrador de autorización de servicio.</span><span class="sxs-lookup"><span data-stu-id="d63e8-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="d63e8-135">Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="d63e8-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="d63e8-136">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d63e8-136">Child elements</span></span>

|<span data-ttu-id="d63e8-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="d63e8-137">Element</span></span>|<span data-ttu-id="d63e8-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="d63e8-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d63e8-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="d63e8-139">authorizationPolicies</span></span>|<span data-ttu-id="d63e8-140">Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="d63e8-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="d63e8-141">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="d63e8-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="d63e8-142">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="d63e8-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="d63e8-143">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="d63e8-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="d63e8-144">Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="d63e8-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="d63e8-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d63e8-145">Parent elements</span></span>

|<span data-ttu-id="d63e8-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="d63e8-146">Element</span></span>|<span data-ttu-id="d63e8-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="d63e8-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d63e8-148">comportamiento de \<></span><span class="sxs-lookup"><span data-stu-id="d63e8-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d63e8-149">Contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="d63e8-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="d63e8-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d63e8-150">Remarks</span></span>

<span data-ttu-id="d63e8-151">Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="d63e8-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="d63e8-152">El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.</span><span class="sxs-lookup"><span data-stu-id="d63e8-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="d63e8-153">El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="d63e8-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="d63e8-154">También puede especificar `UseAspNetRoles` para usar un proveedor de roles personalizado que esté configurado en el elemento de > \<System. Web, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d63e8-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="d63e8-155">En el código siguiente se muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`:</span><span class="sxs-lookup"><span data-stu-id="d63e8-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="d63e8-156">Para obtener un ejemplo detallado del uso de este elemento de configuración, vea [autorizar el acceso a las operaciones de servicio y a](../../../wcf/samples/authorizing-access-to-service-operations.md) la [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d63e8-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d63e8-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="d63e8-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="d63e8-158">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d63e8-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d63e8-159">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="d63e8-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="d63e8-160">Creación de un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="d63e8-160">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="d63e8-161">Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class</span><span class="sxs-lookup"><span data-stu-id="d63e8-161">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="d63e8-162">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="d63e8-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

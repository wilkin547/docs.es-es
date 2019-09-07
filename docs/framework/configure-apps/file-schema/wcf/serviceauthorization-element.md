---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b636b7006900ecff1be553cf32105df7cea7e800
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399691"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="2e07f-102">\<serviceAuthorization >, elemento</span><span class="sxs-lookup"><span data-stu-id="2e07f-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="2e07f-103">Especifica valores que autorizan que el acceso repare las operaciones</span><span class="sxs-lookup"><span data-stu-id="2e07f-103">Specifies settings that authorize access to service operations</span></span>  
  
<span data-ttu-id="2e07f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e07f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e07f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2e07f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2e07f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e07f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2e07f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e07f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2e07f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e07f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2e07f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceAuthorization**</span><span class="sxs-lookup"><span data-stu-id="2e07f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e07f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e07f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e07f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2e07f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2e07f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2e07f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e07f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2e07f-113">Attributes</span></span>  
  
|<span data-ttu-id="2e07f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="2e07f-114">Attribute</span></span>|<span data-ttu-id="2e07f-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2e07f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e07f-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="2e07f-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="2e07f-117">Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2e07f-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="2e07f-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="2e07f-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2e07f-119">Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="2e07f-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="2e07f-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="2e07f-120">principalPermissionMode</span></span>|<span data-ttu-id="2e07f-121">Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2e07f-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="2e07f-122">Los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e07f-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="2e07f-123">-Ninguno</span><span class="sxs-lookup"><span data-stu-id="2e07f-123">-   None</span></span><br /><span data-ttu-id="2e07f-124">-   UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="2e07f-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="2e07f-125">-   UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="2e07f-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="2e07f-126">-Personalizado</span><span class="sxs-lookup"><span data-stu-id="2e07f-126">-   Custom</span></span><br /><br /> <span data-ttu-id="2e07f-127">El valor predeterminado es UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="2e07f-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="2e07f-128">El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="2e07f-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="2e07f-129">Para obtener más información sobre el uso de este [atributo, consulte Cómo: Restrinja el acceso con la clase](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)PrincipalPermissionAttribute.</span><span class="sxs-lookup"><span data-stu-id="2e07f-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="2e07f-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="2e07f-130">roleProviderName</span></span>|<span data-ttu-id="2e07f-131">Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2e07f-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="2e07f-132">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="2e07f-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="2e07f-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="2e07f-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="2e07f-134">Una cadena que contiene el tipo de administrador de autorización de servicio.</span><span class="sxs-lookup"><span data-stu-id="2e07f-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="2e07f-135">Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="2e07f-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e07f-136">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2e07f-136">Child Elements</span></span>  
  
|<span data-ttu-id="2e07f-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e07f-137">Element</span></span>|<span data-ttu-id="2e07f-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2e07f-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e07f-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="2e07f-139">authorizationPolicies</span></span>|<span data-ttu-id="2e07f-140">Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="2e07f-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="2e07f-141">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="2e07f-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="2e07f-142">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="2e07f-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2e07f-143">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="2e07f-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="2e07f-144">Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="2e07f-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e07f-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2e07f-145">Parent Elements</span></span>  
  
|<span data-ttu-id="2e07f-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e07f-146">Element</span></span>|<span data-ttu-id="2e07f-147">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2e07f-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e07f-148">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2e07f-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2e07f-149">Contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="2e07f-149">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e07f-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e07f-150">Remarks</span></span>  
 <span data-ttu-id="2e07f-151">Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="2e07f-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="2e07f-152">El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.</span><span class="sxs-lookup"><span data-stu-id="2e07f-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="2e07f-153">El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="2e07f-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="2e07f-154">También puede especificar `UseAspNetRoles` que se use un proveedor de roles personalizado que esté configurado en \<el elemento System. Web >, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e07f-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="2e07f-155">El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.</span><span class="sxs-lookup"><span data-stu-id="2e07f-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="2e07f-156">Para obtener un ejemplo detallado del uso de este elemento de configuración, vea [autorizar el acceso a las operaciones de servicio y a](../../../wcf/samples/authorizing-access-to-service-operations.md) la [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2e07f-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e07f-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e07f-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="2e07f-158">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="2e07f-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2e07f-159">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="2e07f-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="2e07f-160">Procedimientos: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="2e07f-160">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="2e07f-161">Procedimientos: Restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="2e07f-161">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="2e07f-162">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="2e07f-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

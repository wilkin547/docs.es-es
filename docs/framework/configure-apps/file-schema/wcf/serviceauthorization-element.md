---
description: 'Más información acerca de: <serviceAuthorization> elemento'
title: <serviceAuthorization> (elemento)
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: ee447f487027ed12f829dd0fd364556ce095d7d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682935"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="c56e3-103">Elemento \<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="c56e3-103">\<serviceAuthorization> element</span></span>

<span data-ttu-id="c56e3-104">Especifica valores que autorizan que el acceso repare las operaciones</span><span class="sxs-lookup"><span data-stu-id="c56e3-104">Specifies settings that authorize access to service operations</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

## <a name="syntax"></a><span data-ttu-id="c56e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c56e3-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c56e3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c56e3-106">Attributes and elements</span></span>

<span data-ttu-id="c56e3-107">En las secciones siguientes se describen los atributos, los elementos secundarios y los elementos primarios:</span><span class="sxs-lookup"><span data-stu-id="c56e3-107">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="c56e3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c56e3-108">Attributes</span></span>

|<span data-ttu-id="c56e3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c56e3-109">Attribute</span></span>|<span data-ttu-id="c56e3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c56e3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c56e3-111">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="c56e3-111">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="c56e3-112">Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c56e3-112">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="c56e3-113">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="c56e3-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="c56e3-114">Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="c56e3-114">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="c56e3-115">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="c56e3-115">principalPermissionMode</span></span>|<span data-ttu-id="c56e3-116">Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c56e3-116">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="c56e3-117">Los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c56e3-117">Values include the following:</span></span><br /><br /> <span data-ttu-id="c56e3-118">-Ninguno</span><span class="sxs-lookup"><span data-stu-id="c56e3-118">-   None</span></span><br /><span data-ttu-id="c56e3-119">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="c56e3-119">-   UseWindowsGroups</span></span><br /><span data-ttu-id="c56e3-120">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="c56e3-120">-   UseAspNetRoles</span></span><br /><span data-ttu-id="c56e3-121">-Personalizado</span><span class="sxs-lookup"><span data-stu-id="c56e3-121">-   Custom</span></span><br /><br /> <span data-ttu-id="c56e3-122">El valor predeterminado es UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="c56e3-122">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="c56e3-123">El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="c56e3-123">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="c56e3-124">Para obtener más información sobre el uso de este atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="c56e3-124">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="c56e3-125">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="c56e3-125">roleProviderName</span></span>|<span data-ttu-id="c56e3-126">Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c56e3-126">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c56e3-127">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="c56e3-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="c56e3-128">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="c56e3-128">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="c56e3-129">Una cadena que contiene el tipo de administrador de autorización de servicio.</span><span class="sxs-lookup"><span data-stu-id="c56e3-129">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="c56e3-130">Para obtener más información, vea <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="c56e3-130">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="c56e3-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c56e3-131">Child elements</span></span>

|<span data-ttu-id="c56e3-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="c56e3-132">Element</span></span>|<span data-ttu-id="c56e3-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="c56e3-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c56e3-134">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="c56e3-134">authorizationPolicies</span></span>|<span data-ttu-id="c56e3-135">Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="c56e3-135">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="c56e3-136">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="c56e3-136">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="c56e3-137">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="c56e3-137">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c56e3-138">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="c56e3-138">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="c56e3-139">Para obtener más información, vea <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="c56e3-139">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="c56e3-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c56e3-140">Parent elements</span></span>

|<span data-ttu-id="c56e3-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="c56e3-141">Element</span></span>|<span data-ttu-id="c56e3-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="c56e3-142">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c56e3-143">Contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="c56e3-143">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="c56e3-144">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c56e3-144">Remarks</span></span>

<span data-ttu-id="c56e3-145">Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="c56e3-145">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="c56e3-146">El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.</span><span class="sxs-lookup"><span data-stu-id="c56e3-146">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="c56e3-147">El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="c56e3-147">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="c56e3-148">También puede especificar `UseAspNetRoles` que se use un proveedor de roles personalizado que esté configurado en el \<system.web> elemento, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c56e3-148">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="c56e3-149">En el código siguiente se muestra el `roleProviderName` utilizado con el `principalPermissionMode` atributo:</span><span class="sxs-lookup"><span data-stu-id="c56e3-149">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="c56e3-150">Para obtener un ejemplo detallado del uso de este elemento de configuración, vea [autorizar el acceso a las operaciones de servicio y a](../../../wcf/samples/authorizing-access-to-service-operations.md) la [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c56e3-150">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c56e3-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c56e3-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="c56e3-152">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="c56e3-152">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c56e3-153">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="c56e3-153">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="c56e3-154">Procedimiento para crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="c56e3-154">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="c56e3-155">Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="c56e3-155">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="c56e3-156">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="c56e3-156">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

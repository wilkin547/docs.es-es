---
title: '&lt;userNameAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: d81bf3441f4999683b9dc9ab956fff517c20e80e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754868"
---
# <a name="ltusernameauthenticationgt"></a><span data-ttu-id="d870e-102">&lt;userNameAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="d870e-102">&lt;userNameAuthentication&gt;</span></span>
<span data-ttu-id="d870e-103">Especifica las credenciales de un servicio basadas en el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="d870e-103">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="d870e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d870e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d870e-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d870e-105">\<behaviors></span></span>  
<span data-ttu-id="d870e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d870e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d870e-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d870e-107">\<behavior></span></span>  
<span data-ttu-id="d870e-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d870e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="d870e-109">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="d870e-109">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d870e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d870e-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication  
   cacheLogonTokenLifetime="TimeSpan"  
   cacheLogonTokens="Boolean"   
   customUserNamePasswordValidatorType="String"  
   includeWindowsGroups="Boolean"   
   maxCacheLogonTokens="Integer"  
   membershipProviderName="String"  
   userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d870e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d870e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d870e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d870e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d870e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d870e-113">Attributes</span></span>  
  
|<span data-ttu-id="d870e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d870e-114">Attribute</span></span>|<span data-ttu-id="d870e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d870e-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="d870e-116"><xref:System.TimeSpan> que especifica la duración máxima que un token está almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d870e-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="d870e-117">El valor predeterminado es 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="d870e-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="d870e-118">Un valor booleano que especifica si los tokens de inicio de sesión están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d870e-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="d870e-119">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="d870e-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="d870e-120">Una cadena que especifica el tipo de validador de contraseña de nombre de usuario personalizado que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="d870e-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="d870e-121">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d870e-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="d870e-122">Un valor booleano que especifica si los grupos de Windows están incluidos en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d870e-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="d870e-123">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d870e-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="d870e-124">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="d870e-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="d870e-125">Establezca esta propiedad en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="d870e-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="d870e-126">Un entero que especifica el número máximo de tokens de inicio de sesión para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d870e-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="d870e-127">Este valor debería ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d870e-127">This value should be larger than zero.</span></span> <span data-ttu-id="d870e-128">El valor predeterminado es 128.</span><span class="sxs-lookup"><span data-stu-id="d870e-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="d870e-129">Cuando el atributo `clientCredentialType` de un enlace está establecido en `username`, el nombre de usuario está asignado a las cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="d870e-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="d870e-130">Puede invalidar este comportamiento mediante este atributo, que es una cadena que contiene el nombre del valor <xref:System.Web.Security.MembershipProvider> que proporciona el mecanismo de validación de contraseña pertinente.</span><span class="sxs-lookup"><span data-stu-id="d870e-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="d870e-131">Especifica la manera en la que se valida la contraseña del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="d870e-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="d870e-132">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="d870e-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="d870e-133">-Windows</span><span class="sxs-lookup"><span data-stu-id="d870e-133">-   Windows</span></span><br /><span data-ttu-id="d870e-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="d870e-134">-   MembershipProvider</span></span><br /><span data-ttu-id="d870e-135">-Custom</span><span class="sxs-lookup"><span data-stu-id="d870e-135">-   Custom</span></span><br /><br /> <span data-ttu-id="d870e-136">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="d870e-136">The default is Windows.</span></span> <span data-ttu-id="d870e-137">Este atributo es del tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="d870e-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d870e-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d870e-138">Child Elements</span></span>  
 <span data-ttu-id="d870e-139">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d870e-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d870e-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d870e-140">Parent Elements</span></span>  
  
|<span data-ttu-id="d870e-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="d870e-141">Element</span></span>|<span data-ttu-id="d870e-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="d870e-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d870e-143">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="d870e-143">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="d870e-144">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="d870e-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d870e-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d870e-145">Remarks</span></span>  
 <span data-ttu-id="d870e-146">Si ninguno de los enlaces utilizados por un servicio se configura para la autenticación mediante el nombre de usuario/contraseña, se omiten los atributos para este elemento.</span><span class="sxs-lookup"><span data-stu-id="d870e-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="d870e-147">Entre estos se incluyen los eventos `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` y `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="d870e-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="d870e-148">Si ninguno de los enlaces utilizados por un servicio configurado para utilizar la autenticación de Windows para el nombre de usuario/contraseña, se omite la configuración relacionada con almacenar en memoria caché los tokens de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="d870e-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="d870e-149">Éstos incluyen `cacheLogonTokenLifetime`, `cacheLogonTokens` y `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="d870e-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d870e-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="d870e-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UserNameServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>

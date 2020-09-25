---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178039"
---
# \<userNameAuthentication>

<span data-ttu-id="32768-101">Especifica las credenciales de un servicio basadas en el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="32768-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="32768-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32768-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32768-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32768-103">Attributes and Elements</span></span>  

 <span data-ttu-id="32768-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32768-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32768-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="32768-105">Attributes</span></span>  
  
|<span data-ttu-id="32768-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="32768-106">Attribute</span></span>|<span data-ttu-id="32768-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="32768-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="32768-108"><xref:System.TimeSpan> que especifica la duración máxima que un token está almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="32768-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="32768-109">El valor predeterminado es 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="32768-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="32768-110">Un valor booleano que especifica si los tokens de inicio de sesión están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="32768-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="32768-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="32768-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="32768-112">Una cadena que especifica el tipo de validador de contraseña de nombre de usuario personalizado que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="32768-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="32768-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="32768-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="32768-114">Un valor booleano que especifica si los grupos de Windows están incluidos en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="32768-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="32768-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="32768-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="32768-116">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="32768-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="32768-117">Establezca esta propiedad en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="32768-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="32768-118">Un entero que especifica el número máximo de tokens de inicio de sesión para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="32768-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="32768-119">Este valor debería ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="32768-119">This value should be larger than zero.</span></span> <span data-ttu-id="32768-120">El valor predeterminado es 128.</span><span class="sxs-lookup"><span data-stu-id="32768-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="32768-121">Cuando el atributo `clientCredentialType` de un enlace está establecido en `username`, el nombre de usuario está asignado a las cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="32768-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="32768-122">Puede invalidar este comportamiento mediante este atributo, que es una cadena que contiene el nombre del valor <xref:System.Web.Security.MembershipProvider> que proporciona el mecanismo de validación de contraseña pertinente.</span><span class="sxs-lookup"><span data-stu-id="32768-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="32768-123">Especifica la manera en la que se valida la contraseña del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="32768-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="32768-124">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="32768-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="32768-125">-Windows</span><span class="sxs-lookup"><span data-stu-id="32768-125">-   Windows</span></span><br /><span data-ttu-id="32768-126">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="32768-126">-   MembershipProvider</span></span><br /><span data-ttu-id="32768-127">-Personalizado</span><span class="sxs-lookup"><span data-stu-id="32768-127">-   Custom</span></span><br /><br /> <span data-ttu-id="32768-128">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="32768-128">The default is Windows.</span></span> <span data-ttu-id="32768-129">Este atributo es del tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="32768-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32768-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32768-130">Child Elements</span></span>  

 <span data-ttu-id="32768-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="32768-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32768-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32768-132">Parent Elements</span></span>  
  
|<span data-ttu-id="32768-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="32768-133">Element</span></span>|<span data-ttu-id="32768-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="32768-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="32768-135">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="32768-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32768-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="32768-136">Remarks</span></span>  

 <span data-ttu-id="32768-137">Si ninguno de los enlaces utilizados por un servicio se configura para la autenticación mediante el nombre de usuario/contraseña, se omiten los atributos para este elemento.</span><span class="sxs-lookup"><span data-stu-id="32768-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="32768-138">Entre estos se incluyen los eventos `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` y `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="32768-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="32768-139">Si ninguno de los enlaces utilizados por un servicio configurado para utilizar la autenticación de Windows para el nombre de usuario/contraseña, se omite la configuración relacionada con almacenar en memoria caché los tokens de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="32768-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="32768-140">Éstos incluyen `cacheLogonTokenLifetime`, `cacheLogonTokens` y `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="32768-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32768-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32768-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>

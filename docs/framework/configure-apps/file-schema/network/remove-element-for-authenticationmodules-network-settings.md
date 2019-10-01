---
title: Elemento <remove> para authenticationModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 9b73c0dc1fe161616c08ef0501241d55e9fea9bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697928"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="20144-102">\<remove > elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20144-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="20144-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20144-103">Removes an authentication module from the application.</span></span>  
  
[<span data-ttu-id="20144-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="20144-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="20144-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="20144-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="20144-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="20144-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="20144-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="20144-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20144-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20144-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20144-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20144-109">Attributes and Elements</span></span>  
 <span data-ttu-id="20144-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20144-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20144-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="20144-111">Attributes</span></span>  
  
|<span data-ttu-id="20144-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="20144-112">**Attribute**</span></span>|<span data-ttu-id="20144-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="20144-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="20144-114">**type**</span><span class="sxs-lookup"><span data-stu-id="20144-114">**type**</span></span>|<span data-ttu-id="20144-115">Nombre del módulo de autenticación que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="20144-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20144-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20144-116">Child Elements</span></span>  
 <span data-ttu-id="20144-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="20144-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20144-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20144-118">Parent Elements</span></span>  
  
|<span data-ttu-id="20144-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="20144-119">**Element**</span></span>|<span data-ttu-id="20144-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="20144-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="20144-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="20144-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="20144-122">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="20144-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20144-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20144-123">Remarks</span></span>  
 <span data-ttu-id="20144-124">El elemento `remove` quita los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="20144-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="20144-125">El valor del atributo `type` debe ser un nombre de clase válido.</span><span class="sxs-lookup"><span data-stu-id="20144-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="20144-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="20144-126">Configuration Files</span></span>  
 <span data-ttu-id="20144-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="20144-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20144-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20144-128">Example</span></span>  
 <span data-ttu-id="20144-129">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="20144-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20144-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="20144-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="20144-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="20144-131">Network Settings Schema</span></span>](index.md)

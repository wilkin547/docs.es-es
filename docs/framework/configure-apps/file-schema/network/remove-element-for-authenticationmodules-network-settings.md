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
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154782"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="4a39f-102">\<remove> Element for authenticationModules (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4a39f-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="4a39f-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a39f-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="4a39f-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a39f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a39f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4a39f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4a39f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4a39f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="4a39f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="4a39f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4a39f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a39f-108">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a39f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4a39f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4a39f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4a39f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a39f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a39f-111">Attributes</span></span>  
  
|<span data-ttu-id="4a39f-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="4a39f-112">**Attribute**</span></span>|<span data-ttu-id="4a39f-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4a39f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="4a39f-114">**tipo**</span><span class="sxs-lookup"><span data-stu-id="4a39f-114">**type**</span></span>|<span data-ttu-id="4a39f-115">El nombre del módulo de autenticación que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="4a39f-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a39f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4a39f-116">Child Elements</span></span>  
 <span data-ttu-id="4a39f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4a39f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a39f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4a39f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4a39f-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4a39f-119">**Element**</span></span>|<span data-ttu-id="4a39f-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4a39f-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a39f-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="4a39f-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="4a39f-122">Especifica los módulos utilizados para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="4a39f-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a39f-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4a39f-123">Remarks</span></span>  
 <span data-ttu-id="4a39f-124">El `remove` elemento quita los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="4a39f-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="4a39f-125">El valor `type` del atributo debe ser un nombre de clase válido.</span><span class="sxs-lookup"><span data-stu-id="4a39f-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4a39f-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4a39f-126">Configuration Files</span></span>  
 <span data-ttu-id="4a39f-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4a39f-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a39f-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a39f-128">Example</span></span>  
 <span data-ttu-id="4a39f-129">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4a39f-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a39f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a39f-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="4a39f-131">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="4a39f-131">Network Settings Schema</span></span>](index.md)

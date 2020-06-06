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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154782"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="262cf-102">Elemento \<remove> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="262cf-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="262cf-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="262cf-103">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="262cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="262cf-104">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="262cf-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="262cf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="262cf-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="262cf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="262cf-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="262cf-107">Attributes</span></span>  
  
|<span data-ttu-id="262cf-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="262cf-108">**Attribute**</span></span>|<span data-ttu-id="262cf-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="262cf-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="262cf-110">**type**</span><span class="sxs-lookup"><span data-stu-id="262cf-110">**type**</span></span>|<span data-ttu-id="262cf-111">Nombre del módulo de autenticación que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="262cf-111">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="262cf-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="262cf-112">Child Elements</span></span>  
 <span data-ttu-id="262cf-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="262cf-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="262cf-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="262cf-114">Parent Elements</span></span>  
  
|<span data-ttu-id="262cf-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="262cf-115">**Element**</span></span>|<span data-ttu-id="262cf-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="262cf-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="262cf-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="262cf-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="262cf-118">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="262cf-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="262cf-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="262cf-119">Remarks</span></span>  
 <span data-ttu-id="262cf-120">El `remove` elemento quita los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="262cf-120">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="262cf-121">El valor del `type` atributo debe ser un nombre de clase válido.</span><span class="sxs-lookup"><span data-stu-id="262cf-121">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="262cf-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="262cf-122">Configuration Files</span></span>  
 <span data-ttu-id="262cf-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="262cf-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="262cf-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="262cf-124">Example</span></span>  
 <span data-ttu-id="262cf-125">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="262cf-125">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="262cf-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="262cf-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="262cf-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="262cf-127">Network Settings Schema</span></span>](index.md)

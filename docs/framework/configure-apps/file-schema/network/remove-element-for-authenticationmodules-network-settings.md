---
description: 'Más información sobre: <remove> elemento para authenticationModules (configuración de red)'
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
ms.openlocfilehash: 7c97cd20717e6e0945cf77ad6584b319120ec6a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804093"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="a1ea1-103">Elemento \<remove> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a1ea1-103">\<remove> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="a1ea1-104">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-104">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="a1ea1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1ea1-105">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1ea1-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a1ea1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a1ea1-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1ea1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a1ea1-108">Attributes</span></span>  
  
|<span data-ttu-id="a1ea1-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="a1ea1-109">**Attribute**</span></span>|<span data-ttu-id="a1ea1-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a1ea1-110">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="a1ea1-111">**type**</span><span class="sxs-lookup"><span data-stu-id="a1ea1-111">**type**</span></span>|<span data-ttu-id="a1ea1-112">Nombre del módulo de autenticación que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-112">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1ea1-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1ea1-113">Child Elements</span></span>  

 <span data-ttu-id="a1ea1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1ea1-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1ea1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a1ea1-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="a1ea1-116">**Element**</span></span>|<span data-ttu-id="a1ea1-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a1ea1-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a1ea1-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="a1ea1-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="a1ea1-119">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1ea1-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1ea1-120">Remarks</span></span>  

 <span data-ttu-id="a1ea1-121">El `remove` elemento quita los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-121">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="a1ea1-122">El valor del `type` atributo debe ser un nombre de clase válido.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-122">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a1ea1-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a1ea1-123">Configuration Files</span></span>  

 <span data-ttu-id="a1ea1-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a1ea1-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ea1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1ea1-125">Example</span></span>  

 <span data-ttu-id="a1ea1-126">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a1ea1-126">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1ea1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1ea1-127">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="a1ea1-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a1ea1-128">Network Settings Schema</span></span>](index.md)

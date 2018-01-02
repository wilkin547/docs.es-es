---
title: "&lt;quitar&gt; elemento para authenticationModules (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 077a6f3cb7020d501978fa112a0c318efee27e27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="ff648-102">&lt;quitar&gt; elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="ff648-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="ff648-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff648-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="ff648-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ff648-104">\<configuration></span></span>  
<span data-ttu-id="ff648-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="ff648-105">\<system.net></span></span>  
<span data-ttu-id="ff648-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="ff648-106">\<authenticationModules></span></span>  
<span data-ttu-id="ff648-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="ff648-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff648-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff648-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff648-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff648-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff648-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ff648-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff648-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff648-111">Attributes</span></span>  
  
|<span data-ttu-id="ff648-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="ff648-112">**Attribute**</span></span>|<span data-ttu-id="ff648-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ff648-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ff648-114">**type**</span><span class="sxs-lookup"><span data-stu-id="ff648-114">**type**</span></span>|<span data-ttu-id="ff648-115">El nombre del módulo de autenticación para quitar.</span><span class="sxs-lookup"><span data-stu-id="ff648-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff648-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff648-116">Child Elements</span></span>  
 <span data-ttu-id="ff648-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ff648-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff648-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff648-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ff648-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="ff648-119">**Element**</span></span>|<span data-ttu-id="ff648-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ff648-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ff648-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="ff648-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="ff648-122">Especifica los módulos utilizados para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="ff648-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff648-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff648-123">Remarks</span></span>  
 <span data-ttu-id="ff648-124">El `remove` elemento quita módulos de autenticación definidos anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff648-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="ff648-125">El valor de la `type` atributo debe ser un nombre de clase válida.</span><span class="sxs-lookup"><span data-stu-id="ff648-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ff648-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ff648-126">Configuration Files</span></span>  
 <span data-ttu-id="ff648-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ff648-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff648-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff648-128">Example</span></span>  
 <span data-ttu-id="ff648-129">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="ff648-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff648-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff648-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="ff648-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="ff648-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

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
ms.openlocfilehash: eb8490241d4ec8a34a76aa6087c1f4d27d5cebb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="62755-102">&lt;quitar&gt; elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="62755-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="62755-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62755-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="62755-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="62755-104">\<configuration></span></span>  
<span data-ttu-id="62755-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="62755-105">\<system.net></span></span>  
<span data-ttu-id="62755-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="62755-106">\<authenticationModules></span></span>  
<span data-ttu-id="62755-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="62755-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62755-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62755-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62755-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62755-109">Attributes and Elements</span></span>  
 <span data-ttu-id="62755-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="62755-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62755-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="62755-111">Attributes</span></span>  
  
|<span data-ttu-id="62755-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="62755-112">**Attribute**</span></span>|<span data-ttu-id="62755-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="62755-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="62755-114">**type**</span><span class="sxs-lookup"><span data-stu-id="62755-114">**type**</span></span>|<span data-ttu-id="62755-115">El nombre del módulo de autenticación para quitar.</span><span class="sxs-lookup"><span data-stu-id="62755-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62755-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62755-116">Child Elements</span></span>  
 <span data-ttu-id="62755-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="62755-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62755-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62755-118">Parent Elements</span></span>  
  
|<span data-ttu-id="62755-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="62755-119">**Element**</span></span>|<span data-ttu-id="62755-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="62755-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="62755-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="62755-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="62755-122">Especifica los módulos utilizados para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="62755-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62755-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62755-123">Remarks</span></span>  
 <span data-ttu-id="62755-124">El `remove` elemento quita módulos de autenticación definidos anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="62755-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="62755-125">El valor de la `type` atributo debe ser un nombre de clase válida.</span><span class="sxs-lookup"><span data-stu-id="62755-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="62755-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="62755-126">Configuration Files</span></span>  
 <span data-ttu-id="62755-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="62755-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62755-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62755-128">Example</span></span>  
 <span data-ttu-id="62755-129">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="62755-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62755-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="62755-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="62755-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="62755-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

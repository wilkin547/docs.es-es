---
title: '&lt;Borrar&gt; elemento para authenticationModules (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: b2f5194cc6a4c7c0329edb2a1718a642781f79b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563423"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="f540f-102">&lt;Borrar&gt; elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f540f-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="f540f-103">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f540f-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="f540f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f540f-104">\<configuration></span></span>  
<span data-ttu-id="f540f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f540f-105">\<system.net></span></span>  
<span data-ttu-id="f540f-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="f540f-106">\<authenticationModules></span></span>  
<span data-ttu-id="f540f-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="f540f-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f540f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f540f-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f540f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f540f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f540f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f540f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f540f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f540f-111">Attributes</span></span>  
 <span data-ttu-id="f540f-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f540f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f540f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f540f-113">Child Elements</span></span>  
 <span data-ttu-id="f540f-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f540f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f540f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f540f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f540f-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="f540f-116">**Element**</span></span>|<span data-ttu-id="f540f-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f540f-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f540f-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="f540f-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="f540f-119">Especifica los módulos que se usa para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="f540f-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f540f-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f540f-120">Remarks</span></span>  
 <span data-ttu-id="f540f-121">El `clear` elemento quita todos los módulos de autenticación definidos anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="f540f-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f540f-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f540f-122">Configuration Files</span></span>  
 <span data-ttu-id="f540f-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f540f-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f540f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f540f-124">Example</span></span>  
 <span data-ttu-id="f540f-125">El ejemplo siguiente quita todos los módulos de autenticación configurado.</span><span class="sxs-lookup"><span data-stu-id="f540f-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f540f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f540f-126">See also</span></span>
- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="f540f-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f540f-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

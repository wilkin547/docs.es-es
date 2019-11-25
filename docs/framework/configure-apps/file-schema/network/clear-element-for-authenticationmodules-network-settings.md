---
title: Elemento <clear> para authenticationModules (configuración de red)
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
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087511"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="fd848-102">\<borrar > elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="fd848-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="fd848-103">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd848-103">Clears all authentication modules from the application.</span></span>  

<span data-ttu-id="fd848-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd848-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd848-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd848-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="fd848-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules**](authenticationmodules-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="fd848-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="fd848-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="fd848-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fd848-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd848-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd848-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd848-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fd848-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd848-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd848-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd848-111">Attributes</span></span>  
 <span data-ttu-id="fd848-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd848-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd848-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd848-113">Child Elements</span></span>  
 <span data-ttu-id="fd848-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd848-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd848-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd848-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fd848-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="fd848-116">**Element**</span></span>|<span data-ttu-id="fd848-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fd848-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fd848-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="fd848-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="fd848-119">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="fd848-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd848-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd848-120">Remarks</span></span>  
 <span data-ttu-id="fd848-121">El elemento `clear` quita todos los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="fd848-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fd848-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fd848-122">Configuration Files</span></span>  
 <span data-ttu-id="fd848-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fd848-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd848-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd848-124">Example</span></span>  
 <span data-ttu-id="fd848-125">En el ejemplo siguiente se quitan todos los módulos de autenticación configurados.</span><span class="sxs-lookup"><span data-stu-id="fd848-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd848-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd848-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="fd848-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="fd848-127">Network Settings Schema</span></span>](index.md)

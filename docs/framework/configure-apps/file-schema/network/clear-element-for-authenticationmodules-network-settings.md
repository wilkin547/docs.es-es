---
description: 'Más información sobre: <clear> elemento para authenticationModules (configuración de red)'
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
ms.openlocfilehash: ccfc9f53ef53268cdb1155673fc47a862a63419c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698575"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="f4d4f-103">Elemento \<clear> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f4d4f-103">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="f4d4f-104">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-104">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="f4d4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4d4f-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4d4f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f4d4f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f4d4f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4d4f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f4d4f-108">Attributes</span></span>  

 <span data-ttu-id="f4d4f-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4d4f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f4d4f-110">Child Elements</span></span>  

 <span data-ttu-id="f4d4f-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4d4f-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f4d4f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="f4d4f-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="f4d4f-113">**Element**</span></span>|<span data-ttu-id="f4d4f-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f4d4f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f4d4f-115">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="f4d4f-115">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="f4d4f-116">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-116">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4d4f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4d4f-117">Remarks</span></span>  

 <span data-ttu-id="f4d4f-118">El `clear` elemento quita todos los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-118">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f4d4f-119">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f4d4f-119">Configuration Files</span></span>  

 <span data-ttu-id="f4d4f-120">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f4d4f-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4d4f-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4d4f-121">Example</span></span>  

 <span data-ttu-id="f4d4f-122">En el ejemplo siguiente se quitan todos los módulos de autenticación configurados.</span><span class="sxs-lookup"><span data-stu-id="f4d4f-122">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4d4f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4d4f-123">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="f4d4f-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f4d4f-124">Network Settings Schema</span></span>](index.md)

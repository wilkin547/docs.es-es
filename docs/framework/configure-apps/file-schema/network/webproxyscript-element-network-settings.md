---
description: 'Más información acerca de: <webProxyScript> elemento (configuración de red)'
title: Elemento <webProxyScript> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: 1627b6650582202f3f1a4c1fdebf2d183e4a894b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740111"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="5be8d-103">Elemento \<webProxyScript> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5be8d-103">\<webProxyScript> Element (Network Settings)</span></span>

<span data-ttu-id="5be8d-104">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="5be8d-104">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="5be8d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5be8d-105">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be8d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5be8d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5be8d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5be8d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be8d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5be8d-108">Attributes</span></span>  
  
|<span data-ttu-id="5be8d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5be8d-109">Attribute</span></span>|<span data-ttu-id="5be8d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5be8d-110">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="5be8d-111">Especifica el tiempo máximo para descargar el script en horas, minutos y segundos.</span><span class="sxs-lookup"><span data-stu-id="5be8d-111">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="5be8d-112">El valor predeterminado es un minuto.</span><span class="sxs-lookup"><span data-stu-id="5be8d-112">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be8d-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5be8d-113">Child Elements</span></span>  

 <span data-ttu-id="5be8d-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5be8d-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5be8d-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5be8d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5be8d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5be8d-116">Element</span></span>|<span data-ttu-id="5be8d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5be8d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be8d-118">settings</span><span class="sxs-lookup"><span data-stu-id="5be8d-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="5be8d-119">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="5be8d-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5be8d-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5be8d-120">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5be8d-121">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5be8d-121">Configuration Files</span></span>  

 <span data-ttu-id="5be8d-122">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5be8d-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be8d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5be8d-123">See also</span></span>

- [<span data-ttu-id="5be8d-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5be8d-124">Network Settings Schema</span></span>](index.md)

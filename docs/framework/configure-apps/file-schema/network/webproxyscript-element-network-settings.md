---
title: Elemento <webProxyScript> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089055"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="c0a8d-102">\<elemento > webProxyScript (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c0a8d-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="c0a8d-103">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

<span data-ttu-id="c0a8d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0a8d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0a8d-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c0a8d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c0a8d-106">&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<\** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c0a8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="c0a8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webProxyScript >**</span><span class="sxs-lookup"><span data-stu-id="c0a8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c0a8d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0a8d-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0a8d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c0a8d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0a8d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0a8d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0a8d-111">Attributes</span></span>  
  
|<span data-ttu-id="c0a8d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c0a8d-112">Attribute</span></span>|<span data-ttu-id="c0a8d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0a8d-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="c0a8d-114">Especifica el tiempo máximo para descargar el script en horas, minutos y segundos.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="c0a8d-115">El valor predeterminado es un minuto.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0a8d-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c0a8d-116">Child Elements</span></span>  
 <span data-ttu-id="c0a8d-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0a8d-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c0a8d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c0a8d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0a8d-119">Element</span></span>|<span data-ttu-id="c0a8d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0a8d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0a8d-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="c0a8d-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c0a8d-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c0a8d-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a8d-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0a8d-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0a8d-124">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c0a8d-124">Configuration Files</span></span>  
 <span data-ttu-id="c0a8d-125">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c0a8d-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a8d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0a8d-126">See also</span></span>

- [<span data-ttu-id="c0a8d-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c0a8d-127">Network Settings Schema</span></span>](index.md)

---
title: '&lt;webProxyScript&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e1450d2df424b32aacc5c113b5936001f65915a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085656"
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="133c0-102">&lt;webProxyScript&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="133c0-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="133c0-103">Configura las características de la secuencia de comandos que se usa para detectar a servidores proxy Web.</span><span class="sxs-lookup"><span data-stu-id="133c0-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="133c0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="133c0-104">\<configuration></span></span>  
<span data-ttu-id="133c0-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="133c0-105">\<system.net></span></span>  
<span data-ttu-id="133c0-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="133c0-106">\<settings></span></span>  
<span data-ttu-id="133c0-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="133c0-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133c0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="133c0-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="133c0-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="133c0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="133c0-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="133c0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="133c0-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="133c0-111">Attributes</span></span>  
  
|<span data-ttu-id="133c0-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="133c0-112">Attribute</span></span>|<span data-ttu-id="133c0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c0-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="133c0-114">Especifica el tiempo máximo para descargar el script en horas, minutos y segundos.</span><span class="sxs-lookup"><span data-stu-id="133c0-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="133c0-115">El valor predeterminado es un minuto.</span><span class="sxs-lookup"><span data-stu-id="133c0-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="133c0-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="133c0-116">Child Elements</span></span>  
 <span data-ttu-id="133c0-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="133c0-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="133c0-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="133c0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="133c0-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="133c0-119">Element</span></span>|<span data-ttu-id="133c0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="133c0-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="133c0-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="133c0-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="133c0-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="133c0-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="133c0-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="133c0-124">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="133c0-124">Configuration Files</span></span>  
 <span data-ttu-id="133c0-125">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="133c0-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133c0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="133c0-126">See Also</span></span>  
 [<span data-ttu-id="133c0-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="133c0-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

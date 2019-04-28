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
ms.openlocfilehash: e73ba86cc17fa51cbf4030f2304ab9141fcc0f26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674379"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="de4df-102">\<webProxyScript > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="de4df-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="de4df-103">Configura las características de la secuencia de comandos que se usa para detectar a servidores proxy Web.</span><span class="sxs-lookup"><span data-stu-id="de4df-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="de4df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="de4df-104">\<configuration></span></span>  
<span data-ttu-id="de4df-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="de4df-105">\<system.net></span></span>  
<span data-ttu-id="de4df-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="de4df-106">\<settings></span></span>  
<span data-ttu-id="de4df-107">\<webProxyScript></span><span class="sxs-lookup"><span data-stu-id="de4df-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4df-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de4df-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de4df-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de4df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="de4df-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="de4df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de4df-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="de4df-111">Attributes</span></span>  
  
|<span data-ttu-id="de4df-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="de4df-112">Attribute</span></span>|<span data-ttu-id="de4df-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="de4df-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="de4df-114">Especifica el tiempo máximo para descargar el script en horas, minutos y segundos.</span><span class="sxs-lookup"><span data-stu-id="de4df-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="de4df-115">El valor predeterminado es un minuto.</span><span class="sxs-lookup"><span data-stu-id="de4df-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de4df-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de4df-116">Child Elements</span></span>  
 <span data-ttu-id="de4df-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="de4df-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de4df-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de4df-118">Parent Elements</span></span>  
  
|<span data-ttu-id="de4df-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="de4df-119">Element</span></span>|<span data-ttu-id="de4df-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="de4df-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de4df-121">settings</span><span class="sxs-lookup"><span data-stu-id="de4df-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="de4df-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="de4df-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de4df-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de4df-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="de4df-124">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="de4df-124">Configuration Files</span></span>  
 <span data-ttu-id="de4df-125">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="de4df-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4df-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4df-126">See also</span></span>

- [<span data-ttu-id="de4df-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="de4df-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

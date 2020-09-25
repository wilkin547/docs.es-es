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
ms.openlocfilehash: e36b470b1ec348085b13a58630b0ac6833e43946
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178312"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="fab3d-102">Elemento \<webProxyScript> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="fab3d-102">\<webProxyScript> Element (Network Settings)</span></span>

<span data-ttu-id="fab3d-103">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="fab3d-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="fab3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fab3d-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fab3d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fab3d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fab3d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fab3d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fab3d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="fab3d-107">Attributes</span></span>  
  
|<span data-ttu-id="fab3d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="fab3d-108">Attribute</span></span>|<span data-ttu-id="fab3d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab3d-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="fab3d-110">Especifica el tiempo máximo para descargar el script en horas, minutos y segundos.</span><span class="sxs-lookup"><span data-stu-id="fab3d-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="fab3d-111">El valor predeterminado es un minuto.</span><span class="sxs-lookup"><span data-stu-id="fab3d-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fab3d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fab3d-112">Child Elements</span></span>  

 <span data-ttu-id="fab3d-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fab3d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fab3d-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fab3d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fab3d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fab3d-115">Element</span></span>|<span data-ttu-id="fab3d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab3d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fab3d-117">settings</span><span class="sxs-lookup"><span data-stu-id="fab3d-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="fab3d-118">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="fab3d-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fab3d-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fab3d-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fab3d-120">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fab3d-120">Configuration Files</span></span>  

 <span data-ttu-id="fab3d-121">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fab3d-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab3d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fab3d-122">See also</span></span>

- [<span data-ttu-id="fab3d-123">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="fab3d-123">Network Settings Schema</span></span>](index.md)

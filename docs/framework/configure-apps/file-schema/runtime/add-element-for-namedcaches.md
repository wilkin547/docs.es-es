---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154510"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="1087e-102">Elemento \<add> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="1087e-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="1087e-103">Agrega una `namedCache` entrada a la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1087e-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="1087e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1087e-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="1087e-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="1087e-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1087e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1087e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1087e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1087e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1087e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1087e-108">Attributes</span></span>  
  
|<span data-ttu-id="1087e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1087e-109">Attribute</span></span>|<span data-ttu-id="1087e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1087e-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="1087e-111">Valor entero que especifica el tamaño máximo permitido (en megabytes) que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="1087e-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="1087e-112">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="1087e-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="1087e-113">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1087e-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="1087e-114">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="1087e-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="1087e-115">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="1087e-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="1087e-116">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="1087e-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="1087e-117">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="1087e-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1087e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1087e-118">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="1087e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1087e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1087e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1087e-120">Element</span></span>|<span data-ttu-id="1087e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1087e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="1087e-122">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="1087e-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1087e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1087e-123">Remarks</span></span>  
 <span data-ttu-id="1087e-124">El `add` elemento agrega una entrada a la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1087e-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="1087e-125">Puede usar el elemento [Clear](clear-element-for-namedcaches.md) antes de usar el `add` elemento para asegurarse de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="1087e-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="1087e-126">Este elemento se puede utilizar en el archivo Machine. config y en el archivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="1087e-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1087e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1087e-127">Example</span></span>  
 <span data-ttu-id="1087e-128">En el ejemplo siguiente se muestra cómo definir la configuración de la `namedCache` entrada predeterminada en la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1087e-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1087e-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1087e-129">See also</span></span>

- [<span data-ttu-id="1087e-130">\<namedCaches>(Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="1087e-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)

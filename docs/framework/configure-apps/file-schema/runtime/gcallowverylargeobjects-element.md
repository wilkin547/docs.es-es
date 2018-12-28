---
title: '&lt;gcAllowVeryLargeObjects&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5e0a443f86848a446a7233a2c2e80f693cae9be
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611417"
---
# <a name="ltgcallowverylargeobjectsgt-element"></a><span data-ttu-id="3db74-102">&lt;gcAllowVeryLargeObjects&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="3db74-102">&lt;gcAllowVeryLargeObjects&gt; Element</span></span>
<span data-ttu-id="3db74-103">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="3db74-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="3db74-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="3db74-104">\<configuration> Element</span></span>  
<span data-ttu-id="3db74-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="3db74-105">\<runtime> Element</span></span>  
<span data-ttu-id="3db74-106">\<gcAllowVeryLargeObjects > elemento</span><span class="sxs-lookup"><span data-stu-id="3db74-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db74-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3db74-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3db74-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3db74-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3db74-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3db74-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3db74-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3db74-110">Attributes</span></span>  
  
|<span data-ttu-id="3db74-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="3db74-111">Attribute</span></span>|<span data-ttu-id="3db74-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3db74-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3db74-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3db74-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3db74-114">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3db74-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3db74-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="3db74-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3db74-116">Valor</span><span class="sxs-lookup"><span data-stu-id="3db74-116">Value</span></span>|<span data-ttu-id="3db74-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3db74-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3db74-118">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="3db74-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="3db74-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3db74-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3db74-120">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="3db74-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3db74-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3db74-121">Child Elements</span></span>  
 <span data-ttu-id="3db74-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3db74-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3db74-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3db74-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3db74-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3db74-124">Element</span></span>|<span data-ttu-id="3db74-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3db74-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3db74-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3db74-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3db74-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3db74-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3db74-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3db74-128">Remarks</span></span>  
 <span data-ttu-id="3db74-129">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="3db74-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="3db74-130">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3db74-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="3db74-131">El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.</span><span class="sxs-lookup"><span data-stu-id="3db74-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="3db74-132">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="3db74-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3db74-133">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="3db74-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="3db74-134">Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="3db74-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db74-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3db74-135">Example</span></span>  
 <span data-ttu-id="3db74-136">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3db74-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3db74-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3db74-137">See Also</span></span>  
- [<span data-ttu-id="3db74-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3db74-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="3db74-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3db74-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: <gcAllowVeryLargeObjects> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154132"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="91bb1-102">\<gcAllowVeryLargeObjects> Element</span><span class="sxs-lookup"><span data-stu-id="91bb1-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="91bb1-103">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="91bb1-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="91bb1-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91bb1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91bb1-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="91bb1-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="91bb1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span><span class="sxs-lookup"><span data-stu-id="91bb1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91bb1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91bb1-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91bb1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91bb1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="91bb1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91bb1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91bb1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="91bb1-110">Attributes</span></span>  
  
|<span data-ttu-id="91bb1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="91bb1-111">Attribute</span></span>|<span data-ttu-id="91bb1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="91bb1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="91bb1-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="91bb1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="91bb1-114">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="91bb1-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="91bb1-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="91bb1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="91bb1-116">Value</span><span class="sxs-lookup"><span data-stu-id="91bb1-116">Value</span></span>|<span data-ttu-id="91bb1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="91bb1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="91bb1-118">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="91bb1-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="91bb1-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91bb1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="91bb1-120">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="91bb1-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91bb1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91bb1-121">Child Elements</span></span>  
 <span data-ttu-id="91bb1-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91bb1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91bb1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91bb1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91bb1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="91bb1-124">Element</span></span>|<span data-ttu-id="91bb1-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="91bb1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91bb1-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91bb1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="91bb1-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="91bb1-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91bb1-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91bb1-128">Remarks</span></span>  
 <span data-ttu-id="91bb1-129">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="91bb1-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="91bb1-130">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91bb1-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="91bb1-131">El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.</span><span class="sxs-lookup"><span data-stu-id="91bb1-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="91bb1-132">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="91bb1-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="91bb1-133">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="91bb1-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="91bb1-134">Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="91bb1-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91bb1-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91bb1-135">Example</span></span>  
 <span data-ttu-id="91bb1-136">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="91bb1-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="91bb1-137">Compatible con</span><span class="sxs-lookup"><span data-stu-id="91bb1-137">Supported in</span></span>

<span data-ttu-id="91bb1-138">.NET Framework 4.5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="91bb1-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="91bb1-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91bb1-139">See also</span></span>

- [<span data-ttu-id="91bb1-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="91bb1-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91bb1-141">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="91bb1-141">Configuration File Schema</span></span>](../index.md)

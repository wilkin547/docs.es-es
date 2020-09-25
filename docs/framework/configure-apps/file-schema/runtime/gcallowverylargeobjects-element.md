---
title: <gcAllowVeryLargeObjects> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 78a42596aae6c3ea0d94ac759d11ed52d0ace539
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178234"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="31a1b-102">\<gcAllowVeryLargeObjects> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="31a1b-102">\<gcAllowVeryLargeObjects> Element</span></span>

<span data-ttu-id="31a1b-103">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="31a1b-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="31a1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31a1b-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31a1b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31a1b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="31a1b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31a1b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31a1b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="31a1b-107">Attributes</span></span>  
  
|<span data-ttu-id="31a1b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="31a1b-108">Attribute</span></span>|<span data-ttu-id="31a1b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a1b-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="31a1b-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="31a1b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="31a1b-111">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="31a1b-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="31a1b-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="31a1b-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="31a1b-113">Value</span><span class="sxs-lookup"><span data-stu-id="31a1b-113">Value</span></span>|<span data-ttu-id="31a1b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a1b-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="31a1b-115">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="31a1b-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="31a1b-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="31a1b-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="31a1b-117">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="31a1b-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31a1b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31a1b-118">Child Elements</span></span>  

 <span data-ttu-id="31a1b-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="31a1b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31a1b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31a1b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="31a1b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="31a1b-121">Element</span></span>|<span data-ttu-id="31a1b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a1b-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="31a1b-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31a1b-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="31a1b-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="31a1b-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31a1b-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31a1b-125">Remarks</span></span>  

 <span data-ttu-id="31a1b-126">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="31a1b-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="31a1b-127">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31a1b-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="31a1b-128">El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.</span><span class="sxs-lookup"><span data-stu-id="31a1b-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="31a1b-129">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="31a1b-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="31a1b-130">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="31a1b-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="31a1b-131">Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="31a1b-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a1b-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31a1b-132">Example</span></span>  

 <span data-ttu-id="31a1b-133">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="31a1b-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="31a1b-134">Compatible con</span><span class="sxs-lookup"><span data-stu-id="31a1b-134">Supported in</span></span>

<span data-ttu-id="31a1b-135">.NET Framework 4,5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="31a1b-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="31a1b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31a1b-136">See also</span></span>

- [<span data-ttu-id="31a1b-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="31a1b-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="31a1b-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="31a1b-138">Configuration File Schema</span></span>](../index.md)

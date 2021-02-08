---
description: 'Más información acerca de: <gcAllowVeryLargeObjects> elemento'
title: gcAllowVeryLargeObjects (elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: ff8380a13c4284cc24178e185344207c3b9a39b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787024"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="12627-103">Elemento \<gcAllowVeryLargeObjects></span><span class="sxs-lookup"><span data-stu-id="12627-103">\<gcAllowVeryLargeObjects> element</span></span>

<span data-ttu-id="12627-104">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="12627-104">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="12627-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12627-105">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a><span data-ttu-id="12627-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="12627-106">Attributes</span></span>
  
|<span data-ttu-id="12627-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="12627-107">Attribute</span></span>|<span data-ttu-id="12627-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="12627-108">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="12627-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="12627-109">Required attribute.</span></span><br /><br /> <span data-ttu-id="12627-110">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="12627-110">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="12627-111">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="12627-111">enabled attribute</span></span>  
  
|<span data-ttu-id="12627-112">Value</span><span class="sxs-lookup"><span data-stu-id="12627-112">Value</span></span>|<span data-ttu-id="12627-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="12627-113">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="12627-114">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="12627-114">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="12627-115">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12627-115">This is the default.</span></span>|  
|`true`|<span data-ttu-id="12627-116">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="12627-116">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="12627-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="12627-117">Child elements</span></span>  

<span data-ttu-id="12627-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="12627-118">None.</span></span>  
  
## <a name="parent-elements"></a><span data-ttu-id="12627-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="12627-119">Parent elements</span></span>
  
|<span data-ttu-id="12627-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="12627-120">Element</span></span>|<span data-ttu-id="12627-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="12627-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="12627-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12627-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="12627-123">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="12627-123">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12627-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12627-124">Remarks</span></span>  

 <span data-ttu-id="12627-125">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="12627-125">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="12627-126">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12627-126">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="12627-127">El tamaño máximo de una sola dimensión es 2.147.483.591 (0x7FFFFFC7) para las matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para las matrices que contienen otros tipos.</span><span class="sxs-lookup"><span data-stu-id="12627-127">The maximum size in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for arrays containing other types.</span></span>  
  
- <span data-ttu-id="12627-128">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="12627-128">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="12627-129">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="12627-129">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="12627-130">Por ejemplo, el código no seguro que utiliza matrices como búferes podría ser susceptible a saturaciones del búfer si se escribe en la suposición de que las matrices no superarán los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="12627-130">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it's written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12627-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12627-131">Example</span></span>  

 <span data-ttu-id="12627-132">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="12627-132">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="12627-133">Compatible con</span><span class="sxs-lookup"><span data-stu-id="12627-133">Supported in</span></span>

<span data-ttu-id="12627-134">.NET Framework 4,5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="12627-134">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="12627-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="12627-135">See also</span></span>

- [<span data-ttu-id="12627-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="12627-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="12627-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="12627-137">Configuration File Schema</span></span>](../index.md)

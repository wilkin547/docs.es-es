---
title: gcAllowVeryLargeObjects (elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058134"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="8c424-102">Elemento \<gcAllowVeryLargeObjects></span><span class="sxs-lookup"><span data-stu-id="8c424-102">\<gcAllowVeryLargeObjects> element</span></span>

<span data-ttu-id="8c424-103">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="8c424-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="8c424-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c424-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a><span data-ttu-id="8c424-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c424-105">Attributes</span></span>
  
|<span data-ttu-id="8c424-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="8c424-106">Attribute</span></span>|<span data-ttu-id="8c424-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c424-107">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8c424-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8c424-108">Required attribute.</span></span><br /><br /> <span data-ttu-id="8c424-109">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8c424-109">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="8c424-110">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="8c424-110">enabled attribute</span></span>  
  
|<span data-ttu-id="8c424-111">Valor</span><span class="sxs-lookup"><span data-stu-id="8c424-111">Value</span></span>|<span data-ttu-id="8c424-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c424-112">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8c424-113">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="8c424-113">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="8c424-114">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8c424-114">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8c424-115">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8c424-115">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="8c424-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8c424-116">Child elements</span></span>  

<span data-ttu-id="8c424-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c424-117">None.</span></span>  
  
## <a name="parent-elements"></a><span data-ttu-id="8c424-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8c424-118">Parent elements</span></span>
  
|<span data-ttu-id="8c424-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c424-119">Element</span></span>|<span data-ttu-id="8c424-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c424-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c424-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c424-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8c424-122">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8c424-122">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c424-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c424-123">Remarks</span></span>  

 <span data-ttu-id="8c424-124">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="8c424-124">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="8c424-125">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c424-125">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="8c424-126">El tamaño máximo de una sola dimensión es 2.147.483.591 (0x7FFFFFC7) para las matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para las matrices que contienen otros tipos.</span><span class="sxs-lookup"><span data-stu-id="8c424-126">The maximum size in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for arrays containing other types.</span></span>  
  
- <span data-ttu-id="8c424-127">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="8c424-127">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="8c424-128">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8c424-128">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="8c424-129">Por ejemplo, el código no seguro que utiliza matrices como búferes podría ser susceptible a saturaciones del búfer si se escribe en la suposición de que las matrices no superarán los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8c424-129">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it's written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c424-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c424-130">Example</span></span>  

 <span data-ttu-id="8c424-131">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c424-131">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="8c424-132">Compatible con</span><span class="sxs-lookup"><span data-stu-id="8c424-132">Supported in</span></span>

<span data-ttu-id="8c424-133">.NET Framework 4,5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="8c424-133">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="8c424-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c424-134">See also</span></span>

- [<span data-ttu-id="8c424-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8c424-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8c424-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8c424-136">Configuration File Schema</span></span>](../index.md)

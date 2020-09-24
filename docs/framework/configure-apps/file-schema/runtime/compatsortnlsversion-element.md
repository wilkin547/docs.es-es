---
title: <CompatSortNLSVersion> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
ms.openlocfilehash: 27d532633f08a5a560da61e904917c1faa35126c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151368"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="2d46d-102">\<CompatSortNLSVersion> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="2d46d-102">\<CompatSortNLSVersion> Element</span></span>

<span data-ttu-id="2d46d-103">Especifica que el runtime debe usar criterios de ordenación heredados al realizar comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="2d46d-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**  
  
## <a name="syntax"></a><span data-ttu-id="2d46d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d46d-104">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d46d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d46d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2d46d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d46d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d46d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d46d-107">Attributes</span></span>  
  
|<span data-ttu-id="2d46d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2d46d-108">Attribute</span></span>|<span data-ttu-id="2d46d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d46d-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2d46d-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2d46d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2d46d-111">Especifica el identificador de configuración regional cuyo criterio de ordenación se va a usar.</span><span class="sxs-lookup"><span data-stu-id="2d46d-111">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2d46d-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="2d46d-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="2d46d-113">Valor</span><span class="sxs-lookup"><span data-stu-id="2d46d-113">Value</span></span>|<span data-ttu-id="2d46d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d46d-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d46d-115">4096</span><span class="sxs-lookup"><span data-stu-id="2d46d-115">4096</span></span>|<span data-ttu-id="2d46d-116">El identificador de configuración regional que representa un criterio de ordenación alternativo.</span><span class="sxs-lookup"><span data-stu-id="2d46d-116">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="2d46d-117">En este caso, 4096 representa el criterio de ordenación de los .NET Framework 3,5 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2d46d-117">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d46d-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d46d-118">Child Elements</span></span>  

 <span data-ttu-id="2d46d-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d46d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d46d-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d46d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2d46d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d46d-121">Element</span></span>|<span data-ttu-id="2d46d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d46d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d46d-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d46d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2d46d-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2d46d-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d46d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d46d-125">Remarks</span></span>  

 <span data-ttu-id="2d46d-126">Dado que las operaciones de comparación de cadenas, ordenación y uso de mayúsculas y minúsculas realizadas por la <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> clase en el .NET Framework 4 se ajustan al estándar Unicode 5,1, los resultados de los métodos de comparación de cadenas como <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> y <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> pueden diferir de las versiones anteriores de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d46d-126">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="2d46d-127">Si su aplicación depende del comportamiento heredado, puede restaurar las reglas de comparación y ordenación de cadenas usadas en el .NET Framework 3,5 y versiones anteriores incluyendo el `<CompatSortNLSVersion>` elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d46d-127">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2d46d-128">La restauración de reglas de comparación y ordenación de cadenas heredadas también requiere que la biblioteca de vínculos dinámicos sort00001000.dll esté disponible en el sistema local.</span><span class="sxs-lookup"><span data-stu-id="2d46d-128">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="2d46d-129">También puede usar reglas de ordenación y comparación de cadenas heredadas en un dominio de aplicación concreto. Para ello, pase la cadena "NetFx40_Legacy20SortingBehavior" al método <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> al crear el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d46d-129">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d46d-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d46d-130">Example</span></span>  

 <span data-ttu-id="2d46d-131">En el ejemplo siguiente, se crean instancias de dos objetos <xref:System.String> y se llama al método <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> para compararlas usando las convenciones de la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="2d46d-131">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="2d46d-132">Al ejecutar el ejemplo en el .NET Framework 4, se muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2d46d-132">When you run the example on the .NET Framework 4, it displays the following output:</span></span>
  
```console
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="2d46d-133">Esto es completamente diferente de la salida que se muestra al ejecutar el ejemplo en el .NET Framework 3,5:</span><span class="sxs-lookup"><span data-stu-id="2d46d-133">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5:</span></span>
  
```console
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="2d46d-134">Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en el .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="2d46d-134">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d46d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d46d-135">See also</span></span>

- [<span data-ttu-id="2d46d-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2d46d-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2d46d-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2d46d-137">Configuration File Schema</span></span>](../index.md)

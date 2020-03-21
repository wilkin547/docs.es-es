---
title: <UseRandomizedStringHashAlgorithm> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153782"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="040c6-102">\<UseRandomizedStringHashAlgorithm> Element</span><span class="sxs-lookup"><span data-stu-id="040c6-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="040c6-103">Determina si Common Language Runtime calcula códigos hash para cadenas por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="040c6-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="040c6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="040c6-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="040c6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="040c6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span><span class="sxs-lookup"><span data-stu-id="040c6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040c6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="040c6-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="040c6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="040c6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="040c6-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="040c6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="040c6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="040c6-110">Attributes</span></span>  
  
|<span data-ttu-id="040c6-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="040c6-111">Attribute</span></span>|<span data-ttu-id="040c6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="040c6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="040c6-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="040c6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="040c6-114">Especifica si los códigos hash para cadenas se calculan por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="040c6-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="040c6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="040c6-116">Value</span><span class="sxs-lookup"><span data-stu-id="040c6-116">Value</span></span>|<span data-ttu-id="040c6-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="040c6-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="040c6-118">Common Language Runtime no calcula códigos hash para cadenas por dominio de aplicación; un solo algoritmo se utiliza para calcular códigos hash de cadena.</span><span class="sxs-lookup"><span data-stu-id="040c6-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="040c6-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="040c6-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="040c6-120">Common Language Runtime calcula los códigos hash para las cadenas por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="040c6-121">Cadenas idénticas en diferentes dominios de aplicación y en diferentes procesos tendrán diferentes códigos hash.</span><span class="sxs-lookup"><span data-stu-id="040c6-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="040c6-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="040c6-122">Child Elements</span></span>  
 <span data-ttu-id="040c6-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="040c6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="040c6-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="040c6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="040c6-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="040c6-125">Element</span></span>|<span data-ttu-id="040c6-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="040c6-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="040c6-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="040c6-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="040c6-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="040c6-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="040c6-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="040c6-129">Remarks</span></span>  
 <span data-ttu-id="040c6-130">De forma <xref:System.StringComparer> predeterminada, <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> la clase y el método usan un único algoritmo hash que genera un código hash coherente entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="040c6-131">Esto equivale a `enabled` establecer el `<UseRandomizedStringHashAlgorithm>` atributo `0`del elemento en .</span><span class="sxs-lookup"><span data-stu-id="040c6-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="040c6-132">Este es el algoritmo hash utilizado en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="040c6-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="040c6-133">La <xref:System.StringComparer> clase <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> y el método también pueden usar un algoritmo hash diferente que calcula los códigos hash por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="040c6-134">Como resultado, los códigos hash para cadenas equivalentes diferirán entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="040c6-135">Esta es una característica opt-in; para aprovecharlo, debe establecer `enabled` el atributo `<UseRandomizedStringHashAlgorithm>` del `1`elemento en .</span><span class="sxs-lookup"><span data-stu-id="040c6-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="040c6-136">La búsqueda de cadenas en una tabla hash suele ser una operación O(1).</span><span class="sxs-lookup"><span data-stu-id="040c6-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="040c6-137">Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una operación O(n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="040c6-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="040c6-138">Puede utilizar `<UseRandomizedStringHashAlgorithm>` el elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de colisiones potenciales, especialmente cuando las claves a partir de las cuales se calculan los códigos hash se basan en la entrada de datos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="040c6-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="040c6-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="040c6-139">Example</span></span>  
 <span data-ttu-id="040c6-140">En el ejemplo `DisplayString` siguiente se define una `s`clase que incluye una constante de cadena privada, cuyo valor es "This is a string."</span><span class="sxs-lookup"><span data-stu-id="040c6-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="040c6-141">También incluye un método `ShowStringHashCode` que presenta el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.</span><span class="sxs-lookup"><span data-stu-id="040c6-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="040c6-142">Cuando ejecute el ejemplo sin proporcionar un archivo de configuración, mostrará un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="040c6-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="040c6-143">Observe que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="040c6-144">Sin embargo, si agrega el archivo de configuración siguiente al directorio de ejemplo y, a continuación, ejecuta el ejemplo, los códigos hash para la misma cadena diferirán en función del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="040c6-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="040c6-145">Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="040c6-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="040c6-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="040c6-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

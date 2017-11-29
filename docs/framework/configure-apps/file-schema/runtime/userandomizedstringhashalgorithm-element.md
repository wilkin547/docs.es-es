---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7cd561cf0e0a9e080b150bdaa412686126423c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="b88ba-102">&lt;UseRandomizedStringHashAlgorithm&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="b88ba-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="b88ba-103">Determina si common language runtime calcula los códigos hash de cadenas en una cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="b88ba-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b88ba-104">\<configuration></span></span>  
<span data-ttu-id="b88ba-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="b88ba-105">\<runtime></span></span>  
<span data-ttu-id="b88ba-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="b88ba-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b88ba-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b88ba-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b88ba-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b88ba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b88ba-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b88ba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b88ba-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b88ba-110">Attributes</span></span>  
  
|<span data-ttu-id="b88ba-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b88ba-111">Attribute</span></span>|<span data-ttu-id="b88ba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b88ba-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b88ba-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b88ba-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b88ba-114">Especifica si los códigos hash de cadenas se calculan en una cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b88ba-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="b88ba-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b88ba-116">Valor</span><span class="sxs-lookup"><span data-stu-id="b88ba-116">Value</span></span>|<span data-ttu-id="b88ba-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b88ba-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="b88ba-118">Common language runtime no calcular los códigos hash de cadenas en una cada dominio de aplicación; se usa un solo algoritmo para calcular los códigos hash de cadena.</span><span class="sxs-lookup"><span data-stu-id="b88ba-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="b88ba-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b88ba-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="b88ba-120">Common language runtime calcula los códigos hash de cadenas en una cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="b88ba-121">Cadenas idénticas en diferentes dominios de aplicación y en diferentes procesos tendrán códigos hash diferentes.</span><span class="sxs-lookup"><span data-stu-id="b88ba-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b88ba-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b88ba-122">Child Elements</span></span>  
 <span data-ttu-id="b88ba-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b88ba-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b88ba-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b88ba-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b88ba-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b88ba-125">Element</span></span>|<span data-ttu-id="b88ba-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b88ba-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b88ba-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b88ba-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b88ba-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b88ba-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b88ba-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b88ba-129">Remarks</span></span>  
 <span data-ttu-id="b88ba-130">De forma predeterminada, el <xref:System.StringComparer> clase y <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método usar un único algoritmo hash que genera un código hash coherente entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="b88ba-131">Esto es equivalente a establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `0`.</span><span class="sxs-lookup"><span data-stu-id="b88ba-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="b88ba-132">Esto es el algoritmo hash utilizado en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b88ba-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="b88ba-133">El <xref:System.StringComparer> clase y <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método también puede utilizar un algoritmo de hash diferente que calcula los códigos hash en un cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="b88ba-134">Como resultado, los códigos hash de cadenas equivalente serán diferentes dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="b88ba-135">Se trata de una característica opcional; Para sacar partido de ella, debe establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `1`.</span><span class="sxs-lookup"><span data-stu-id="b88ba-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="b88ba-136">Normalmente, la búsqueda de cadena en una tabla hash es una operación o (1).</span><span class="sxs-lookup"><span data-stu-id="b88ba-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="b88ba-137">Sin embargo, cuando se produce un gran número de conflictos, la búsqueda puede ser una O (n<sup>2</sup>) operación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="b88ba-138">Puede usar el `<UseRandomizedStringHashAlgorithm>` elemento de configuración que se va a generar un algoritmo hash aleatorios por dominio de aplicación, que a su vez limita el número de posibles conflictos, especialmente cuando las claves de la que se calculan los códigos hash se basan en la entrada de datos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b88ba-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b88ba-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b88ba-139">Example</span></span>  
 <span data-ttu-id="b88ba-140">En el ejemplo siguiente se define un `DisplayString` clase que incluya una constante de cadena privada, `s`, cuyo valor es "Es una cadena".</span><span class="sxs-lookup"><span data-stu-id="b88ba-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="b88ba-141">También incluye una `ShowStringHashCode` método que muestra el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.</span><span class="sxs-lookup"><span data-stu-id="b88ba-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="b88ba-142">Al ejecutar el ejemplo sin proporcionar un archivo de configuración, muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="b88ba-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="b88ba-143">Tenga en cuenta que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="b88ba-144">Sin embargo, si agrega el siguiente archivo de configuración al directorio del ejemplo y, a continuación, ejecutar el ejemplo, los códigos hash de la misma cadena variarán por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b88ba-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b88ba-145">Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b88ba-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="b88ba-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="b88ba-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

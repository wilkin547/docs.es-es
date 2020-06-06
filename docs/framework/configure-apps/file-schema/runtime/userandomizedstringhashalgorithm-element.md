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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153782"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="29887-102">\<UseRandomizedStringHashAlgorithm> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="29887-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="29887-103">Determina si el Common Language Runtime calcula los códigos hash para las cadenas en cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="29887-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29887-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29887-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29887-105">Attributes and Elements</span></span>  
 <span data-ttu-id="29887-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29887-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29887-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="29887-107">Attributes</span></span>  
  
|<span data-ttu-id="29887-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="29887-108">Attribute</span></span>|<span data-ttu-id="29887-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="29887-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="29887-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="29887-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="29887-111">Especifica si los códigos hash para las cadenas se calculan en función de cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="29887-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="29887-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="29887-113">Value</span><span class="sxs-lookup"><span data-stu-id="29887-113">Value</span></span>|<span data-ttu-id="29887-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="29887-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="29887-115">El Common Language Runtime no calcula los códigos hash para las cadenas en cada dominio de aplicación; se usa un solo algoritmo para calcular los códigos hash de la cadena.</span><span class="sxs-lookup"><span data-stu-id="29887-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="29887-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="29887-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="29887-117">El Common Language Runtime calcula los códigos hash para las cadenas en cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="29887-118">Las cadenas idénticas en dominios de aplicación diferentes y en procesos diferentes tendrán códigos hash diferentes.</span><span class="sxs-lookup"><span data-stu-id="29887-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29887-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29887-119">Child Elements</span></span>  
 <span data-ttu-id="29887-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29887-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29887-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29887-121">Parent Elements</span></span>  
  
|<span data-ttu-id="29887-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="29887-122">Element</span></span>|<span data-ttu-id="29887-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="29887-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29887-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29887-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="29887-125">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29887-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29887-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29887-126">Remarks</span></span>  
 <span data-ttu-id="29887-127">De forma predeterminada, la <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método usan un algoritmo hash único que genera un código hash coherente entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="29887-128">Esto es equivalente a establecer el `enabled` atributo del `<UseRandomizedStringHashAlgorithm>` elemento en `0` .</span><span class="sxs-lookup"><span data-stu-id="29887-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="29887-129">Este es el algoritmo hash utilizado en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="29887-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="29887-130">La <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método también pueden usar un algoritmo hash diferente que calcula los códigos hash en cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="29887-131">Como resultado, los códigos hash de las cadenas equivalentes serán diferentes en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="29887-132">Se trata de una característica opcional; para aprovecharlo, debe establecer el `enabled` atributo del `<UseRandomizedStringHashAlgorithm>` elemento en `1` .</span><span class="sxs-lookup"><span data-stu-id="29887-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="29887-133">La búsqueda de cadena en una tabla hash es normalmente una operación O (1).</span><span class="sxs-lookup"><span data-stu-id="29887-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="29887-134">Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una operación O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="29887-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="29887-135">Puede usar el `<UseRandomizedStringHashAlgorithm>` elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de colisiones potenciales, especialmente cuando las claves de las que se calculan los códigos hash se basan en la entrada de datos por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="29887-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29887-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29887-136">Example</span></span>  
 <span data-ttu-id="29887-137">En el ejemplo siguiente se define una `DisplayString` clase que incluye una constante de cadena privada, `s` , cuyo valor es "This is a String".</span><span class="sxs-lookup"><span data-stu-id="29887-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="29887-138">También incluye un método `ShowStringHashCode` que presenta el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.</span><span class="sxs-lookup"><span data-stu-id="29887-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="29887-139">Cuando ejecute el ejemplo sin proporcionar un archivo de configuración, mostrará un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="29887-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="29887-140">Observe que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="29887-141">Sin embargo, si agrega el archivo de configuración siguiente al directorio de ejemplo y, a continuación, ejecuta el ejemplo, los códigos hash para la misma cadena diferirán en función del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29887-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="29887-142">Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="29887-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="29887-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29887-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

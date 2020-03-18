---
title: Realizar cambios de mayúsculas y minúsculas que no tienen en cuenta las referencias culturales
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
ms.openlocfilehash: 7b2dee03619e24c5a2845699a06e88abab0c594b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160136"
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="1d2dc-102">Realizar cambios de mayúsculas y minúsculas que no tienen en cuenta las referencias culturales</span><span class="sxs-lookup"><span data-stu-id="1d2dc-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="1d2dc-103">Los métodos <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> y <xref:System.Char.ToLower%2A?displayProperty=nameWithType> disponen de sobrecargas que no aceptan ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="1d2dc-104">De forma predeterminada, estas sobrecargas sin parámetros realizan cambios de mayúsculas y minúsculas en función del valor de <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1d2dc-105">Esto produce resultados que tienen en cuenta las mayúsculas y minúsculas y que pueden cambiar en función de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="1d2dc-106">Para aclarar si desea cambios de mayúsculas y minúsculas que tengan en cuenta las referencias culturales o que no las tengan en cuenta, debe usar las sobrecargas de esos métodos que necesitan la especificación explícita de un parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="1d2dc-107">En el caso de cambios en el uso de mayúsculas y minúsculas dependientes de la referencia cultural, especifique `CultureInfo.CurrentCulture` para el parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="1d2dc-108">Si se trata de cambios en el uso de mayúsculas y minúsculas independientes de la referencia cultural, especifique `CultureInfo.InvariantCulture` para el parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="1d2dc-109">A menudo, las cadenas se convierten a un uso estándar de mayúsculas y minúsculas, para permitir una búsqueda más fácil posteriormente.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="1d2dc-110">Cuando se usan las cadenas de este modo, se debe especificar `CultureInfo.InvariantCulture` para el parámetro `culture`, ya que el valor de <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> podría cambiar desde el momento en que se hacen los cambios de mayúsculas y minúsculas hasta el momento en que se realiza la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="1d2dc-111">Si una decisión de seguridad se basa en una operación de cambio de mayúsculas y minúsculas, la operación debe ser independiente de la referencia cultural para asegurarse de que el resultado no se vea afectado por el valor de `CultureInfo.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="1d2dc-112">Consulte la sección "Comparaciones de cadenas que usan la referencia cultural actual" del artículo [Prácticas recomendadas para utilizar las cadenas en .NET](../../../docs/standard/base-types/best-practices-strings.md) para obtener un ejemplo que muestra cómo las operaciones de cadenas que tienen en cuenta la referencia cultural pueden generar resultados incoherentes.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="1d2dc-113">Utilizar los métodos String.ToUpper y String.ToLower</span><span class="sxs-lookup"><span data-stu-id="1d2dc-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="1d2dc-114">Para lograr claridad en el código, se recomienda usar siempre sobrecargas de los métodos `String.ToUpper` y `String.ToLower` que permiten especificar explícitamente un parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="1d2dc-115">Por ejemplo, en el siguiente código se realiza la búsqueda de un identificador.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="1d2dc-116">La operación `key.ToLower` tiene en cuenta las referencias culturales de manera predeterminada, pero este comportamiento no está claro leyendo el código.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1d2dc-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d2dc-117">Example</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 <span data-ttu-id="1d2dc-118">Si desea que la operación `key.ToLower` sea independiente de la referencia cultural, debe cambiar el ejemplo anterior de la manera siguiente para usar explícitamente `CultureInfo.InvariantCulture` cuando se cambien las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="1d2dc-119">Utilizar los métodos Char.ToUpper y Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="1d2dc-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="1d2dc-120">Aunque los métodos `Char.ToUpper` y `Char.ToLower` tienen las mismas características que los métodos `String.ToUpper` y `String.ToLower`, las únicas referencias culturales afectadas son la de turco (Turquía) y azerbaiyano (latino, Azerbaiyán).</span><span class="sxs-lookup"><span data-stu-id="1d2dc-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="1d2dc-121">Estas son las dos únicas referencias culturales con diferencias de mayúsculas y minúsculas en un solo carácter.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="1d2dc-122">Para obtener información más detallada sobre esta asignación única de mayúsculas y minúsculas, vea la sección "Uso de mayúsculas y minúsculas" en el tema de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="1d2dc-123">Para lograr claridad en el código y asegurar resultados coherentes, se recomienda usar siempre las sobrecargas de estos métodos que permiten especificar explícitamente un parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="1d2dc-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2dc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d2dc-124">See also</span></span>

- <xref:System.String.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.String.ToLower%2A?displayProperty=nameWithType>
- <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.Char.ToLower%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1d2dc-125">Realizar operaciones de cadenas que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="1d2dc-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)

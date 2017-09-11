---
title: "Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 19e620415adefd6190d3896377eaf6a7cf944f28
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="a5601-102">Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a5601-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="a5601-103">Las *propiedades indexadas* mejoran la manera en que se usan las propiedades COM con parámetros en la programación de C#.</span><span class="sxs-lookup"><span data-stu-id="a5601-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="a5601-104">Las propiedades indexadas funcionan junto con otras características de Visual C#, como los [argumentos con nombre y opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuevo tipo ([dinámico](../../../csharp/language-reference/keywords/dynamic.md)) y la [información de tipo insertada](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), para mejorar la programación en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a5601-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="a5601-105">En versiones anteriores de C#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor.</span><span class="sxs-lookup"><span data-stu-id="a5601-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="a5601-106">En cambio, no todas las propiedades COM cumplen esas restricciones.</span><span class="sxs-lookup"><span data-stu-id="a5601-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="a5601-107">Por ejemplo, la propiedad [Range](http://go.microsoft.com/fwlink/?LinkId=166053) de Excel tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo.</span><span class="sxs-lookup"><span data-stu-id="a5601-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="a5601-108">Antes, como no había acceso directo a la propiedad `Range`, había que usar el método `get_Range` en su lugar, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5601-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a5601-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5601-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span></span>  
  
 <span data-ttu-id="a5601-110">Las propiedades indexadas, en cambio, permiten escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5601-110">Indexed properties enable you to write the following instead:</span></span>  
  
 <span data-ttu-id="a5601-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5601-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5601-112">En el ejemplo anterior, también se usa la característica [argumentos opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), que le permite omitir `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="a5601-112">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="a5601-113">De manera similar, para establecer el valor de la propiedad `Value` de un objeto [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) de Visual C# 2008 y versiones anteriores, se necesitan dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="a5601-113">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="a5601-114">Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo.</span><span class="sxs-lookup"><span data-stu-id="a5601-114">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="a5601-115">El otro proporciona el valor de la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="a5601-115">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="a5601-116">Estas técnicas se ilustran en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a5601-116">The following examples illustrate these techniques.</span></span> <span data-ttu-id="a5601-117">En ambos ejemplos, se establece el valor de la celda A1 en `Name`.</span><span class="sxs-lookup"><span data-stu-id="a5601-117">Both set the value of the A1 cell to `Name`.</span></span>
  
 <span data-ttu-id="a5601-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5601-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span></span>  
  
 <span data-ttu-id="a5601-119">Las propiedades indexadas, en cambio, le permiten escribir el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="a5601-119">Indexed properties enable you to write the following code instead.</span></span>  
  
 <span data-ttu-id="a5601-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5601-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span></span>  
  
 <span data-ttu-id="a5601-121">No es posible crear propiedades indizadas propias.</span><span class="sxs-lookup"><span data-stu-id="a5601-121">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="a5601-122">La característica solo admite el uso de las propiedades indizadas existentes.</span><span class="sxs-lookup"><span data-stu-id="a5601-122">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5601-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5601-123">Example</span></span>  
 <span data-ttu-id="a5601-124">En el código siguiente se muestra un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="a5601-124">The following code shows a complete example.</span></span> <span data-ttu-id="a5601-125">Para obtener más información sobre cómo preparar un proyecto con acceso a la API de Office, vea [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a5601-125">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 <span data-ttu-id="a5601-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5601-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5601-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5601-127">See Also</span></span>  
 <span data-ttu-id="a5601-128">[Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="a5601-128">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 <span data-ttu-id="a5601-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="a5601-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="a5601-130">[Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="a5601-130">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="a5601-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  [Cómo: Usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)]</span><span class="sxs-lookup"><span data-stu-id="a5601-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="a5601-132">[Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a5601-132">[How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span></span>  
 [<span data-ttu-id="a5601-133">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="a5601-133">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)


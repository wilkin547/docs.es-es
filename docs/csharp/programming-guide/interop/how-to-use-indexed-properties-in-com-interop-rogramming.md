---
title: 'Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: d2b992131bb5722b8a10ec4a71fc42602c98a12c
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347626"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="ed6b0-102">Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ed6b0-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="ed6b0-103">Las *propiedades indexadas* mejoran la manera en que se usan las propiedades COM con parámetros en la programación de C#.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="ed6b0-104">Las propiedades indexadas funcionan junto con otras características de Visual C#, como los [argumentos con nombre y opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuevo tipo ([dinámico](../../../csharp/language-reference/keywords/dynamic.md)) y la [información de tipo insertada](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), para mejorar la programación en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="ed6b0-105">En versiones anteriores de C#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="ed6b0-106">En cambio, no todas las propiedades COM cumplen esas restricciones.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="ed6b0-107">Por ejemplo, la propiedad <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> de Excel tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="ed6b0-108">Antes, como no había acceso directo a la propiedad `Range`, había que usar el método `get_Range` en su lugar, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="ed6b0-109">Las propiedades indexadas, en cambio, permiten escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed6b0-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
>  <span data-ttu-id="ed6b0-110">En el ejemplo anterior, también se usa la característica [argumentos opcionales](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), que le permite omitir `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-110">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="ed6b0-111">De manera similar, para establecer el valor de la propiedad `Value` de un objeto <xref:Microsoft.Office.Interop.Excel.Range> en C# 3.0 y versiones anteriores, se necesitan dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="ed6b0-112">Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="ed6b0-113">El otro proporciona el valor de la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="ed6b0-114">Estas técnicas se ilustran en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="ed6b0-115">En ambos ejemplos, se establece el valor de la celda A1 en `Name`.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="ed6b0-116">Las propiedades indexadas, en cambio, le permiten escribir el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="ed6b0-117">No es posible crear propiedades indizadas propias.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="ed6b0-118">La característica solo admite el uso de las propiedades indizadas existentes.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed6b0-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed6b0-119">Example</span></span>  
 <span data-ttu-id="ed6b0-120">En el código siguiente se muestra un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="ed6b0-120">The following code shows a complete example.</span></span> <span data-ttu-id="ed6b0-121">Para obtener más información sobre cómo preparar un proyecto con acceso a la API de Office, consulte [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="ed6b0-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ed6b0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed6b0-122">See also</span></span>

- [<span data-ttu-id="ed6b0-123">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="ed6b0-123">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="ed6b0-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="ed6b0-124">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)
- [<span data-ttu-id="ed6b0-125">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="ed6b0-125">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="ed6b0-126">Cómo: Usar argumentos opcionales y con nombre en la programación de Office</span><span class="sxs-lookup"><span data-stu-id="ed6b0-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="ed6b0-127">Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#</span><span class="sxs-lookup"><span data-stu-id="ed6b0-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="ed6b0-128">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="ed6b0-128">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)

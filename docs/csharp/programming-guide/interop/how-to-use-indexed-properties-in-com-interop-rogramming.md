---
title: 'Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 864e2274f0e0e79b4843e0bb67b5c4384eac8588
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712070"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="f421b-102">Procedimiento Utilizar propiedades indizadas en la programación de interoperabilidad COM (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f421b-102">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>
<span data-ttu-id="f421b-103">Las *propiedades indexadas* mejoran la manera en que se usan las propiedades COM con parámetros en la programación de C#.</span><span class="sxs-lookup"><span data-stu-id="f421b-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="f421b-104">Las propiedades indexadas funcionan junto con otras características de Visual C#, como los [argumentos con nombre y opcionales](../classes-and-structs/named-and-optional-arguments.md), un nuevo tipo ([dinámico](../../language-reference/builtin-types/reference-types.md)) y la [información de tipo insertada](../../../standard/assembly/embed-types-visual-studio.md), para mejorar la programación en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f421b-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="f421b-105">En versiones anteriores de C#, los métodos son solo accesibles como propiedades si el método `get` no tiene ningún parámetro y el método `set` tiene solo un parámetro de valor.</span><span class="sxs-lookup"><span data-stu-id="f421b-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="f421b-106">En cambio, no todas las propiedades COM cumplen esas restricciones.</span><span class="sxs-lookup"><span data-stu-id="f421b-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="f421b-107">Por ejemplo, la propiedad <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> de Excel tiene un descriptor de acceso `get` que requiere un parámetro para el nombre del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f421b-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="f421b-108">Antes, como no había acceso directo a la propiedad `Range`, había que usar el método `get_Range` en su lugar, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f421b-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="f421b-109">Las propiedades indexadas, en cambio, permiten escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f421b-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="f421b-110">En el ejemplo anterior, también se usa la característica [argumentos opcionales](../classes-and-structs/named-and-optional-arguments.md), que le permite omitir `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="f421b-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="f421b-111">De manera similar, para establecer el valor de la propiedad `Value` de un objeto <xref:Microsoft.Office.Interop.Excel.Range> en C# 3.0 y versiones anteriores, se necesitan dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="f421b-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="f421b-112">Uno proporciona un argumento para un parámetro opcional que especifica el tipo del valor del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f421b-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="f421b-113">El otro proporciona el valor de la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="f421b-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="f421b-114">Estas técnicas se ilustran en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f421b-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="f421b-115">En ambos ejemplos, se establece el valor de la celda A1 en `Name`.</span><span class="sxs-lookup"><span data-stu-id="f421b-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="f421b-116">Las propiedades indexadas, en cambio, le permiten escribir el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="f421b-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="f421b-117">No es posible crear propiedades indizadas propias.</span><span class="sxs-lookup"><span data-stu-id="f421b-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="f421b-118">La característica solo admite el uso de las propiedades indizadas existentes.</span><span class="sxs-lookup"><span data-stu-id="f421b-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f421b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f421b-119">Example</span></span>  
 <span data-ttu-id="f421b-120">En el código siguiente se muestra un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="f421b-120">The following code shows a complete example.</span></span> <span data-ttu-id="f421b-121">Para más información sobre cómo preparar un proyecto con acceso a la API de Office, consulte [Procedimiento Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](./how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f421b-121">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="f421b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f421b-122">See also</span></span>

- [<span data-ttu-id="f421b-123">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="f421b-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="f421b-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="f421b-124">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="f421b-125">Uso de tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="f421b-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="f421b-126">Procedimiento para usar argumentos opcionales y con nombre en la programación de Office</span><span class="sxs-lookup"><span data-stu-id="f421b-126">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="f421b-127">Procedimiento para acceder a objetos de interoperabilidad de Office mediante características de C#</span><span class="sxs-lookup"><span data-stu-id="f421b-127">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="f421b-128">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="f421b-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)

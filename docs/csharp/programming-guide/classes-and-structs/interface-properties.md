---
title: 'Propiedades de interfaces: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: fad674c6d56011afcccbe9ce2a88e7af411fe0a2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579154"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="c3a65-102">Propiedades de interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c3a65-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="c3a65-103">Las propiedades se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="c3a65-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="c3a65-104">A continuación se muestra un ejemplo de un descriptor de acceso de propiedad de interfaz:</span><span class="sxs-lookup"><span data-stu-id="c3a65-104">The following is an example of an interface property accessor:</span></span>

[!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]

<span data-ttu-id="c3a65-105">El descriptor de acceso de una propiedad de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c3a65-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="c3a65-106">Por tanto, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="c3a65-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>

## <a name="example"></a><span data-ttu-id="c3a65-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3a65-107">Example</span></span>

<span data-ttu-id="c3a65-108">En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="c3a65-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="c3a65-109">La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="c3a65-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="c3a65-110">El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.</span><span class="sxs-lookup"><span data-stu-id="c3a65-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="c3a65-111">Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro.</span><span class="sxs-lookup"><span data-stu-id="c3a65-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="c3a65-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c3a65-112">For example:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="c3a65-113">Se denomina [implementación de interfaz explícita](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="c3a65-113">This is called [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="c3a65-114">Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria.</span><span class="sxs-lookup"><span data-stu-id="c3a65-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="c3a65-115">Es decir, la siguiente declaración de propiedad:</span><span class="sxs-lookup"><span data-stu-id="c3a65-115">That is, the following property declaration:</span></span>

[!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]

<span data-ttu-id="c3a65-116">implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="c3a65-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]

<span data-ttu-id="c3a65-117">implementa la propiedad `Name` en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="c3a65-117">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="c3a65-118">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3a65-118">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="c3a65-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3a65-119">See also</span></span>

- [<span data-ttu-id="c3a65-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c3a65-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c3a65-121">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c3a65-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="c3a65-122">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="c3a65-122">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="c3a65-123">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="c3a65-123">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="c3a65-124">Indizadores</span><span class="sxs-lookup"><span data-stu-id="c3a65-124">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="c3a65-125">Interfaces</span><span class="sxs-lookup"><span data-stu-id="c3a65-125">Interfaces</span></span>](../interfaces/index.md)

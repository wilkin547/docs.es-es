---
title: 'Propiedades de interfaces: Guía de programación de C#'
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626625"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="02c3f-102">Propiedades de interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="02c3f-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="02c3f-103">Las propiedades se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="02c3f-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="02c3f-104">En el ejemplo siguiente se declara un descriptor de acceso de propiedad de interfaz:</span><span class="sxs-lookup"><span data-stu-id="02c3f-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="02c3f-105">Normalmente, las propiedades de interfaz no tienen un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="02c3f-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="02c3f-106">Los descriptores de acceso indican si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="02c3f-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="02c3f-107">A diferencia de las clases y las estructuras, la declaración de los descriptores de acceso sin cuerpo no declara una [propiedad implementada automáticamente](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="02c3f-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="02c3f-108">A partir de C# 8.0, una interfaz puede definir una implementación predeterminada para los miembros, incluidas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="02c3f-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="02c3f-109">La definición de una implementación predeterminada para una propiedad en una interfaz es poco frecuente, ya que las interfaces no pueden definir campos de datos de instancia.</span><span class="sxs-lookup"><span data-stu-id="02c3f-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="02c3f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02c3f-110">Example</span></span>

<span data-ttu-id="02c3f-111">En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="02c3f-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="02c3f-112">La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="02c3f-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="02c3f-113">El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.</span><span class="sxs-lookup"><span data-stu-id="02c3f-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="02c3f-114">Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro.</span><span class="sxs-lookup"><span data-stu-id="02c3f-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="02c3f-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02c3f-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="02c3f-116">En el ejemplo anterior se muestra la [implementación de interfaz explícita](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="02c3f-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="02c3f-117">Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria.</span><span class="sxs-lookup"><span data-stu-id="02c3f-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="02c3f-118">Es decir, la siguiente declaración de propiedad:</span><span class="sxs-lookup"><span data-stu-id="02c3f-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="02c3f-119">implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="02c3f-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="02c3f-120">implementa la propiedad `Name` en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="02c3f-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="02c3f-121">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="02c3f-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="02c3f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="02c3f-122">See also</span></span>

- [<span data-ttu-id="02c3f-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="02c3f-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="02c3f-124">Propiedades</span><span class="sxs-lookup"><span data-stu-id="02c3f-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="02c3f-125">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="02c3f-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="02c3f-126">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="02c3f-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="02c3f-127">Indizadores</span><span class="sxs-lookup"><span data-stu-id="02c3f-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="02c3f-128">Interfaces</span><span class="sxs-lookup"><span data-stu-id="02c3f-128">Interfaces</span></span>](../interfaces/index.md)

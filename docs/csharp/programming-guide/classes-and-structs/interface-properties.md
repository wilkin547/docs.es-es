---
title: 'Propiedades de interfaces: Guía de programación de C#'
description: Las propiedades se pueden declarar en una interfaz de C#. En este ejemplo se declara un descriptor de acceso de propiedad de interfaz.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864974"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="6edc3-104">Propiedades de interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6edc3-104">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="6edc3-105">Las propiedades se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="6edc3-105">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="6edc3-106">En el ejemplo siguiente se declara un descriptor de acceso de propiedad de interfaz:</span><span class="sxs-lookup"><span data-stu-id="6edc3-106">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="6edc3-107">Normalmente, las propiedades de interfaz no tienen un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="6edc3-107">Interface properties typically don't have a body.</span></span> <span data-ttu-id="6edc3-108">Los descriptores de acceso indican si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="6edc3-108">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="6edc3-109">A diferencia de las clases y las estructuras, la declaración de los descriptores de acceso sin cuerpo no declara una [propiedad implementada automáticamente](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6edc3-109">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="6edc3-110">A partir de C# 8.0, una interfaz puede definir una implementación predeterminada para los miembros, incluidas las propiedades.</span><span class="sxs-lookup"><span data-stu-id="6edc3-110">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="6edc3-111">La definición de una implementación predeterminada para una propiedad en una interfaz es poco frecuente, ya que las interfaces no pueden definir campos de datos de instancia.</span><span class="sxs-lookup"><span data-stu-id="6edc3-111">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="6edc3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6edc3-112">Example</span></span>

<span data-ttu-id="6edc3-113">En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="6edc3-113">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="6edc3-114">La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="6edc3-114">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="6edc3-115">El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.</span><span class="sxs-lookup"><span data-stu-id="6edc3-115">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="6edc3-116">Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro.</span><span class="sxs-lookup"><span data-stu-id="6edc3-116">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="6edc3-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6edc3-117">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6edc3-118">En el ejemplo anterior se muestra la [implementación de interfaz explícita](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="6edc3-118">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="6edc3-119">Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria.</span><span class="sxs-lookup"><span data-stu-id="6edc3-119">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="6edc3-120">Es decir, la siguiente declaración de propiedad:</span><span class="sxs-lookup"><span data-stu-id="6edc3-120">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6edc3-121">implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="6edc3-121">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="6edc3-122">implementa la propiedad `Name` en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="6edc3-122">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="6edc3-123">Salida de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6edc3-123">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="6edc3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6edc3-124">See also</span></span>

- [<span data-ttu-id="6edc3-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6edc3-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6edc3-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6edc3-126">Properties</span></span>](./properties.md)
- [<span data-ttu-id="6edc3-127">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="6edc3-127">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="6edc3-128">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="6edc3-128">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="6edc3-129">Indizadores</span><span class="sxs-lookup"><span data-stu-id="6edc3-129">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="6edc3-130">Interfaces</span><span class="sxs-lookup"><span data-stu-id="6edc3-130">Interfaces</span></span>](../interfaces/index.md)

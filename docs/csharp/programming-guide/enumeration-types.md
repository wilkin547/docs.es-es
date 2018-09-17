---
title: Tipos de enumeración (Guía de programación de C#)
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3efedd48303c79bafde3704b0fdd6fcdd465a0a7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45686133"
---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="2eba5-102">Tipos de enumeración (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2eba5-102">Enumeration types (C# Programming Guide)</span></span>

<span data-ttu-id="2eba5-103">Un tipo de enumeración (también denominado enumeración) proporciona una manera eficaz de definir un conjunto de constantes enteras con nombre que se pueden asignar a una variable.</span><span class="sxs-lookup"><span data-stu-id="2eba5-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="2eba5-104">Por ejemplo, suponga que tiene que definir una variable cuyo valor representará un día de la semana.</span><span class="sxs-lookup"><span data-stu-id="2eba5-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="2eba5-105">Dicha variable solo almacenará siete valores significativos.</span><span class="sxs-lookup"><span data-stu-id="2eba5-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="2eba5-106">Para definir esos valores, puede usar un tipo de enumeración, que se declara mediante la palabra clave [enum](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="2eba5-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

<span data-ttu-id="2eba5-107">De forma predeterminada, el tipo subyacente de cada elemento de la enumeración es [int](../../csharp/language-reference/keywords/int.md). Puede especificar otro tipo numérico entero mediante el uso del signo de dos puntos, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2eba5-107">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md). You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="2eba5-108">Para obtener una lista completa de los tipos posibles, vea [enum (Referencia de C#)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="2eba5-108">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>

<span data-ttu-id="2eba5-109">Puede comprobar los valores numéricos subyacentes mediante la conversión al tipo subyacente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2eba5-109">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

<span data-ttu-id="2eba5-110">Estas son las ventajas de usar una enumeración en lugar de un tipo numérico:</span><span class="sxs-lookup"><span data-stu-id="2eba5-110">The following are advantages of using an enum instead of a numeric type:</span></span>

- <span data-ttu-id="2eba5-111">Se especifica claramente para el código de cliente qué valores son válidos para la variable.</span><span class="sxs-lookup"><span data-stu-id="2eba5-111">You clearly specify for client code which values are valid for the variable.</span></span>

- <span data-ttu-id="2eba5-112">En Visual Studio, IntelliSense muestra los valores definidos.</span><span class="sxs-lookup"><span data-stu-id="2eba5-112">In Visual Studio, IntelliSense lists the defined values.</span></span>

<span data-ttu-id="2eba5-113">Cuando no se especifican valores para los elementos de la lista de enumeradores, los valores se incrementan automáticamente en 1.</span><span class="sxs-lookup"><span data-stu-id="2eba5-113">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="2eba5-114">En el ejemplo anterior, `Day.Sunday` tiene un valor de 0, `Day.Monday` tiene un valor de 1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2eba5-114">In the previous example, `Day.Sunday` has a value of 0, `Day.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="2eba5-115">Cuando cree un nuevo objeto `Day`, tendrá un valor predeterminado de `Day.Sunday` (0) si no le asigna explícitamente un valor.</span><span class="sxs-lookup"><span data-stu-id="2eba5-115">When you create a new `Day` object, it will have a default value of `Day.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="2eba5-116">Cuando cree una enumeración, seleccione el valor predeterminado más lógico y asígnele un valor de cero.</span><span class="sxs-lookup"><span data-stu-id="2eba5-116">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="2eba5-117">Esto hará que todas las enumeraciones tengan ese valor predeterminado si no se les asigna explícitamente un valor cuando se crean.</span><span class="sxs-lookup"><span data-stu-id="2eba5-117">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>

<span data-ttu-id="2eba5-118">Si la variable `meetingDay` es de tipo `Day`, solo puede asignarle (sin una conversión explícita) uno de los valores definidos por `Day`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-118">If the variable `meetingDay` is of type `Day`, then (without an explicit cast) you can only assign it one of the values defined by `Day`.</span></span> <span data-ttu-id="2eba5-119">Si el día de la reunión cambia, puede asignarle un nuevo valor de `Day` a `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="2eba5-119">And if the meeting day changes, you can assign a new value from `Day` to `meetingDay`:</span></span>

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> <span data-ttu-id="2eba5-120">Es posible asignar un valor entero cualquiera a `meetingDay`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-120">It's possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="2eba5-121">Por ejemplo, esta línea de código no genera un error: `meetingDay = (Day) 42`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-121">For example, this line of code does not produce an error: `meetingDay = (Day) 42`.</span></span> <span data-ttu-id="2eba5-122">Pero no debe hacerlo, ya que la expectativa implícita es que una variable de enumeración contenga solamente uno de los valores definidos por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2eba5-122">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="2eba5-123">La acción de asignar un valor arbitrario a una variable de un tipo de enumeración aumenta el riesgo de errores.</span><span class="sxs-lookup"><span data-stu-id="2eba5-123">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>

<span data-ttu-id="2eba5-124">Puede asignar cualquier valor a los elementos de la lista de enumeradores de un tipo de enumeración, y también puede usar valores calculados:</span><span class="sxs-lookup"><span data-stu-id="2eba5-124">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="2eba5-125">Tipos de enumeración como marcas de bits</span><span class="sxs-lookup"><span data-stu-id="2eba5-125">Enumeration types as bit flags</span></span>

<span data-ttu-id="2eba5-126">Puede usar un tipo de enumeración para definir marcas de bits, lo que permite que una instancia del tipo de enumeración almacene cualquier combinación de los valores que se definen en la lista de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="2eba5-126">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="2eba5-127">(Obviamente, es posible que algunas combinaciones no sean significativas o no se permitan en el código del programa).</span><span class="sxs-lookup"><span data-stu-id="2eba5-127">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>

<span data-ttu-id="2eba5-128">Para crear una enumeración de marcas de bits, aplique el atributo <xref:System.FlagsAttribute?displayProperty=nameWithType> y defina los valores de forma adecuada para que se puedan realizar en ellos operaciones bit a bit `AND`, `OR`, `NOT` y `XOR`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-128">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="2eba5-129">En una enumeración de marcas de bits, incluya una constante con nombre con un valor de cero que signifique "no se establecen marcas".</span><span class="sxs-lookup"><span data-stu-id="2eba5-129">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="2eba5-130">No le asigne a una marca un valor de cero si no significa "no se establecen marcas".</span><span class="sxs-lookup"><span data-stu-id="2eba5-130">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>

<span data-ttu-id="2eba5-131">En el ejemplo siguiente, se define otra versión de la enumeración `Day`, denominada `Days`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-131">In the following example, another version of the `Day` enum, which is named `Days`, is defined.</span></span> <span data-ttu-id="2eba5-132">`Days` tiene el atributo `Flags` y a cada valor se le asigna la siguiente potencia de 2 superior.</span><span class="sxs-lookup"><span data-stu-id="2eba5-132">`Days` has the `Flags` attribute, and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="2eba5-133">Esto le permite crear una variable `Days` cuyo valor es `Days.Tuesday | Days.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="2eba5-133">This enables you to create a `Days` variable whose value is `Days.Tuesday | Days.Thursday`.</span></span>

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

<span data-ttu-id="2eba5-134">Para establecer una marca en una enumeración, use el operador bit a bit `OR` tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2eba5-134">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

<span data-ttu-id="2eba5-135">Para determinar si se ha establecido una marca específica, use una operación bit a bit `AND`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2eba5-135">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

<span data-ttu-id="2eba5-136">Para obtener más información sobre lo que debe tener en cuenta para definir tipos de enumeraciones con el atributo <xref:System.FlagsAttribute?displayProperty=nameWithType>, vea <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2eba5-136">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="2eba5-137">Usar los métodos System.Enum para detectar y manipular valores de enumeración</span><span class="sxs-lookup"><span data-stu-id="2eba5-137">Using the System.Enum methods to discover and manipulate enum values</span></span>

<span data-ttu-id="2eba5-138">Todas las enumeraciones son instancias del tipo <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2eba5-138">All enums are instances of the <xref:System.Enum?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="2eba5-139">No se pueden derivar clases nuevas de <xref:System.Enum?displayProperty=nameWithType>, pero puede usar sus métodos para detectar información relacionada y manipular los valores de una instancia de enumeración.</span><span class="sxs-lookup"><span data-stu-id="2eba5-139">You cannot derive new classes from <xref:System.Enum?displayProperty=nameWithType>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

<span data-ttu-id="2eba5-140">Para obtener más información, vea <xref:System.Enum?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2eba5-140">For more information, see <xref:System.Enum?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="2eba5-141">También puede crear un método nuevo para una enumeración mediante un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="2eba5-141">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="2eba5-142">Para obtener más información, vea [Cómo: Crear un método nuevo para una enumeración](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="2eba5-142">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2eba5-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="2eba5-143">See Also</span></span>

- <xref:System.Enum?displayProperty=nameWithType>  
- [<span data-ttu-id="2eba5-144">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2eba5-144">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2eba5-145">enum</span><span class="sxs-lookup"><span data-stu-id="2eba5-145">enum</span></span>](../../csharp/language-reference/keywords/enum.md)

---
title: "Tipos de enumeración (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="f057a-102">Tipos de enumeración (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f057a-102">Enumeration Types (C# Programming Guide)</span></span>
<span data-ttu-id="f057a-103">Un tipo de enumeración (también denominado enumeración) proporciona una manera eficaz de definir un conjunto de constantes enteras con nombre que se pueden asignar a una variable.</span><span class="sxs-lookup"><span data-stu-id="f057a-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="f057a-104">Por ejemplo, suponga que tiene que definir una variable cuyo valor representará un día de la semana.</span><span class="sxs-lookup"><span data-stu-id="f057a-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="f057a-105">Dicha variable solo almacenará siete valores significativos.</span><span class="sxs-lookup"><span data-stu-id="f057a-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="f057a-106">Para definir esos valores, puede usar un tipo de enumeración, que se declara mediante la palabra clave [enum](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="f057a-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>  
  
 <span data-ttu-id="f057a-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span></span>  
  
 <span data-ttu-id="f057a-108">De forma predeterminada, el tipo subyacente de cada elemento de la enumeración es [int](../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="f057a-108">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="f057a-109">Puede especificar otro tipo numérico entero mediante el uso del signo de dos puntos, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f057a-109">You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="f057a-110">Para obtener una lista completa de los tipos posibles, vea [enum (Referencia de C#)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="f057a-110">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="f057a-111">Puede comprobar los valores numéricos subyacentes mediante la conversión al tipo subyacente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f057a-111">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 <span data-ttu-id="f057a-112">Estas son las ventajas de usar una enumeración en lugar de un tipo numérico:</span><span class="sxs-lookup"><span data-stu-id="f057a-112">The following are advantages of using an enum instead of a numeric type:</span></span>  
  
-   <span data-ttu-id="f057a-113">Se especifica claramente para el código de cliente qué valores son válidos para la variable.</span><span class="sxs-lookup"><span data-stu-id="f057a-113">You clearly specify for client code which values are valid for the variable.</span></span>  
  
-   <span data-ttu-id="f057a-114">En [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense muestra los valores definidos.</span><span class="sxs-lookup"><span data-stu-id="f057a-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>  
  
 <span data-ttu-id="f057a-115">Cuando no se especifican valores para los elementos de la lista de enumeradores, los valores se incrementan automáticamente en 1.</span><span class="sxs-lookup"><span data-stu-id="f057a-115">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="f057a-116">En el ejemplo anterior, `Days.Sunday` tiene un valor de 0, `Days.Monday` tiene un valor de 1, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f057a-116">In the previous example, `Days.Sunday` has a value of 0, `Days.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="f057a-117">Cuando cree un nuevo objeto `Days`, tendrá un valor predeterminado de `Days.Sunday` (0) si no le asigna explícitamente un valor.</span><span class="sxs-lookup"><span data-stu-id="f057a-117">When you create a new `Days` object, it will have a default value of `Days.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="f057a-118">Cuando cree una enumeración, seleccione el valor predeterminado más lógico y asígnele un valor de cero.</span><span class="sxs-lookup"><span data-stu-id="f057a-118">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="f057a-119">Esto hará que todas las enumeraciones tengan ese valor predeterminado si no se les asigna explícitamente un valor cuando se crean.</span><span class="sxs-lookup"><span data-stu-id="f057a-119">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>  
  
 <span data-ttu-id="f057a-120">Si la variable `meetingDay` es de tipo `Days`, solo puede asignarle (sin una conversión explícita) uno de los valores definidos por `Days`.</span><span class="sxs-lookup"><span data-stu-id="f057a-120">If the variable `meetingDay` is of type `Days`, then (without an explicit cast) you can only assign it one of the values defined by `Days`.</span></span> <span data-ttu-id="f057a-121">Si el día de la reunión cambia, puede asignarle un nuevo valor de `Days` a `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="f057a-121">And if the meeting day changes, you can assign a new value from `Days` to `meetingDay`:</span></span>  
  
 <span data-ttu-id="f057a-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f057a-123">Es posible asignar un valor entero cualquiera a `meetingDay`.</span><span class="sxs-lookup"><span data-stu-id="f057a-123">It is possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="f057a-124">Por ejemplo, esta línea de código no genera un error: `meetingDay = (Days) 42`.</span><span class="sxs-lookup"><span data-stu-id="f057a-124">For example, this line of code does not produce an error: `meetingDay = (Days) 42`.</span></span> <span data-ttu-id="f057a-125">Pero no debe hacerlo, ya que la expectativa implícita es que una variable de enumeración contenga solamente uno de los valores definidos por la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f057a-125">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="f057a-126">La acción de asignar un valor arbitrario a una variable de un tipo de enumeración aumenta el riesgo de errores.</span><span class="sxs-lookup"><span data-stu-id="f057a-126">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>  
  
 <span data-ttu-id="f057a-127">Puede asignar cualquier valor a los elementos de la lista de enumeradores de un tipo de enumeración, y también puede usar valores calculados:</span><span class="sxs-lookup"><span data-stu-id="f057a-127">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>  
  
 <span data-ttu-id="f057a-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span></span>  
  
## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="f057a-129">Tipos de enumeración como marcas de bits</span><span class="sxs-lookup"><span data-stu-id="f057a-129">Enumeration Types as Bit Flags</span></span>  
 <span data-ttu-id="f057a-130">Puede usar un tipo de enumeración para definir marcas de bits, lo que permite que una instancia del tipo de enumeración almacene cualquier combinación de los valores que se definen en la lista de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="f057a-130">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="f057a-131">(Obviamente, es posible que algunas combinaciones no sean significativas o no se permitan en el código del programa).</span><span class="sxs-lookup"><span data-stu-id="f057a-131">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>  
  
 <span data-ttu-id="f057a-132">Para crear una enumeración de marcas de bits, aplique el atributo <xref:System.FlagsAttribute?displayProperty=fullName> y defina los valores de forma adecuada para que se puedan realizar en ellos operaciones bit a bit `AND`, `OR`, `NOT` y `XOR`.</span><span class="sxs-lookup"><span data-stu-id="f057a-132">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=fullName> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="f057a-133">En una enumeración de marcas de bits, incluya una constante con nombre con un valor de cero que signifique "no se establecen marcas".</span><span class="sxs-lookup"><span data-stu-id="f057a-133">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="f057a-134">No le asigne a una marca un valor de cero si no significa "no se establecen marcas".</span><span class="sxs-lookup"><span data-stu-id="f057a-134">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>  
  
 <span data-ttu-id="f057a-135">En el ejemplo siguiente, se define otra versión de la enumeración `Days`, denominada `Days2`.</span><span class="sxs-lookup"><span data-stu-id="f057a-135">In the following example, another version of the `Days` enum, which is named `Days2`, is defined.</span></span> <span data-ttu-id="f057a-136">`Days2` tiene el atributo `Flags` y a cada valor se le asigna la siguiente potencia de 2 superior.</span><span class="sxs-lookup"><span data-stu-id="f057a-136">`Days2` has the `Flags` attribute and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="f057a-137">Esto le permite crear una variable `Days2` cuyo valor es `Days2.Tuesday` y `Days2.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="f057a-137">This enables you to create a `Days2` variable whose value is `Days2.Tuesday` and `Days2.Thursday`.</span></span>  
  
 <span data-ttu-id="f057a-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span></span>  
  
 <span data-ttu-id="f057a-139">Para establecer una marca en una enumeración, use el operador bit a bit `OR` tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f057a-139">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>  
  
 <span data-ttu-id="f057a-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span></span>  
  
 <span data-ttu-id="f057a-141">Para determinar si se ha establecido una marca específica, use una operación bit a bit `AND`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f057a-141">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>  
  
 <span data-ttu-id="f057a-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span></span>  
  
 <span data-ttu-id="f057a-143">Para obtener más información sobre lo que debe tener en cuenta para definir tipos de enumeraciones con el atributo <xref:System.FlagsAttribute?displayProperty=fullName>, vea <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f057a-143">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=fullName> attribute, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="f057a-144">Usar los métodos System.Enum para detectar y manipular valores de enumeración</span><span class="sxs-lookup"><span data-stu-id="f057a-144">Using the System.Enum Methods to Discover and Manipulate Enum Values</span></span>  
 <span data-ttu-id="f057a-145">Todas las enumeraciones son instancias del tipo <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f057a-145">All enums are instances of the <xref:System.Enum?displayProperty=fullName> type.</span></span> <span data-ttu-id="f057a-146">No se pueden derivar clases nuevas de <xref:System.Enum?displayProperty=fullName>, pero puede usar sus métodos para detectar información relacionada y manipular los valores de una instancia de enumeración.</span><span class="sxs-lookup"><span data-stu-id="f057a-146">You cannot derive new classes from <xref:System.Enum?displayProperty=fullName>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>  
  
 <span data-ttu-id="f057a-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="f057a-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span></span>  
  
 <span data-ttu-id="f057a-148">Para obtener más información, consulta <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f057a-148">For more information, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="f057a-149">También puede crear un método nuevo para una enumeración mediante un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="f057a-149">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="f057a-150">Para obtener más información, vea [Cómo: Crear un método nuevo para una enumeración](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f057a-150">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="f057a-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="f057a-151">See Also</span></span>  
 <span data-ttu-id="f057a-152"><xref:System.Enum?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f057a-152"><xref:System.Enum?displayProperty=fullName></span></span>   
 <span data-ttu-id="f057a-153">[Guía de programación de C#](../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f057a-153">[C# Programming Guide](../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f057a-154">enum</span><span class="sxs-lookup"><span data-stu-id="f057a-154">enum</span></span>](../../csharp/language-reference/keywords/enum.md)


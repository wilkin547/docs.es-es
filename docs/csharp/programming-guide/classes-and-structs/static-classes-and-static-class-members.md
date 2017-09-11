---
title: "Clases estáticas y sus miembros (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: 49
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
ms.openlocfilehash: 63f46f9ae35b3c699744f7bf61cad3b08b796509
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="c692d-102">Clases estáticas y sus miembros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c692d-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="c692d-103">Una clase [estática](../../../csharp/language-reference/keywords/static.md) es básicamente lo mismo que una clase no estática, con la diferencia de que no se pueden crear instancias de una clase estática.</span><span class="sxs-lookup"><span data-stu-id="c692d-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="c692d-104">En otras palabras, no puede usar la palabra clave [new](../../../csharp/language-reference/keywords/new.md) para crear una variable del tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="c692d-105">Dado que no hay ninguna variable de instancia, para tener acceso a los miembros de una clase estática, debe usar el nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="c692d-106">Por ejemplo, si tiene una clase estática denominada `UtilityClass` que tiene un método público denominado `MethodA`, llame al método tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c692d-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="c692d-107">Es posible usar una clase estática como un contenedor adecuado para conjuntos de métodos que solo funcionan en parámetros de entrada y que no tienen que obtener ni establecer campos de instancias internas.</span><span class="sxs-lookup"><span data-stu-id="c692d-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="c692d-108">Por ejemplo, en la biblioteca de clases .NET Framework, la clase estática <xref:System.Math?displayProperty=fullName> contiene métodos que realizan operaciones matemáticas, sin ningún requisito para almacenar o recuperar datos que sean únicos de una instancia concreta de la clase <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="c692d-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=fullName> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="c692d-109">Es decir, para aplicar los miembros de la clase, debe especificar el nombre de clase y el nombre de método, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c692d-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="c692d-110">Como sucede con todos los tipos de clase, Common Language Runtime (CLR) de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] carga la información de tipo para una clase estática cuando se carga el programa que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="c692d-111">El programa no puede especificar exactamente cuándo se carga la clase,</span><span class="sxs-lookup"><span data-stu-id="c692d-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="c692d-112">pero existe la garantía de que se cargará, de que sus campos se inicializarán y de que se llamará a su constructor estático antes de que se haga referencia a la clase por primera vez en el programa.</span><span class="sxs-lookup"><span data-stu-id="c692d-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="c692d-113">Solo se llama una vez a un constructor estático, y una clase estática permanece en memoria durante la vigencia del dominio de aplicación en el que reside el programa.</span><span class="sxs-lookup"><span data-stu-id="c692d-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c692d-114">Para crear una clase no estática que solo permita la creación de una instancia de sí misma, vea [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567) (Implementar un singleton en C#).</span><span class="sxs-lookup"><span data-stu-id="c692d-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span></span>  
  
 <span data-ttu-id="c692d-115">La siguiente lista contiene las características principales de una clase estática:</span><span class="sxs-lookup"><span data-stu-id="c692d-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="c692d-116">Solo contiene miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="c692d-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="c692d-117">No se pueden crear instancias de ella.</span><span class="sxs-lookup"><span data-stu-id="c692d-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="c692d-118">Está sellada.</span><span class="sxs-lookup"><span data-stu-id="c692d-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="c692d-119">No puede contener [constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="c692d-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="c692d-120">Por lo tanto, crear una clase estática es básicamente lo mismo que crear una clase que contiene solo miembros estáticos y un constructor privado.</span><span class="sxs-lookup"><span data-stu-id="c692d-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="c692d-121">Un constructor privado impide que se creen instancias de la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="c692d-122">La ventaja de usar una clase estática es que el compilador puede comprobar que no se agregue accidentalmente ningún miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="c692d-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="c692d-123">El compilador garantizará que no se creen instancias de esta clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="c692d-124">Las clases estáticas están selladas y, por lo tanto, no pueden heredarse.</span><span class="sxs-lookup"><span data-stu-id="c692d-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="c692d-125">No pueden heredar de ninguna clase excepto <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c692d-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="c692d-126">Las clases estáticas no pueden contener un constructor de instancias, pero pueden contener un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="c692d-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="c692d-127">Las clases no estáticas también deben definir un constructor estático si la clase contiene miembros estáticos que requieren inicialización no trivial.</span><span class="sxs-lookup"><span data-stu-id="c692d-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="c692d-128">Para obtener más información, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="c692d-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c692d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c692d-129">Example</span></span>  
 <span data-ttu-id="c692d-130">A continuación se muestra un ejemplo de una clase estática que contiene dos métodos que convierten la temperatura de grados Celsius a grados Fahrenheit y viceversa:</span><span class="sxs-lookup"><span data-stu-id="c692d-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 <span data-ttu-id="c692d-131">[!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c692d-131">[!code-cs[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]</span></span>  
  
## <a name="static-members"></a><span data-ttu-id="c692d-132">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="c692d-132">Static Members</span></span>  
 <span data-ttu-id="c692d-133">Una clase no estática puede contener métodos, campos, propiedades o eventos estáticos.</span><span class="sxs-lookup"><span data-stu-id="c692d-133">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="c692d-134">El miembro estático es invocable en una clase, incluso si no se ha creado ninguna instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-134">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="c692d-135">Siempre se tiene acceso al miembro estático con el nombre de clase, no con el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="c692d-135">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="c692d-136">Solo existe una copia de un miembro estático, independientemente del número de instancias de la clase que se creen.</span><span class="sxs-lookup"><span data-stu-id="c692d-136">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="c692d-137">Los métodos y las propiedades estáticos no pueden tener acceso a campos y eventos no estáticos en su tipo contenedor, y tampoco pueden tener acceso a una variable de instancia de un objeto a menos que se pase explícitamente en un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="c692d-137">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="c692d-138">Es más habitual declarar una clase no estática con algunos miembros estáticos que declarar toda una clase como estática.</span><span class="sxs-lookup"><span data-stu-id="c692d-138">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="c692d-139">Dos usos habituales de los campos estáticos son llevar la cuenta del número de objetos de los que se han creado instancias y almacenar un valor que se debe compartir entre todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="c692d-139">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="c692d-140">Los métodos estáticos se pueden sobrecargar pero no invalidar, ya que pertenecen a la clase y no a una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-140">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="c692d-141">Aunque un campo no se puede declarar como `static const`, el campo [const](../../../csharp/language-reference/keywords/const.md) es básicamente estático en su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c692d-141">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="c692d-142">Pertenece al tipo, no a las instancias del tipo.</span><span class="sxs-lookup"><span data-stu-id="c692d-142">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="c692d-143">Por lo tanto, se puede tener acceso a campos const mediante la misma notación `ClassName.MemberName` que se usa para los campos estáticos.</span><span class="sxs-lookup"><span data-stu-id="c692d-143">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="c692d-144">No se requiere ninguna instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="c692d-144">No object instance is required.</span></span>  
  
 <span data-ttu-id="c692d-145">C# no admite variables locales estáticas (variables que se declaran en el ámbito del método).</span><span class="sxs-lookup"><span data-stu-id="c692d-145">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="c692d-146">Para declarar miembros de clases estáticas, use la palabra clave `static` antes del tipo de valor devuelto del miembro, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c692d-146">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 <span data-ttu-id="c692d-147">[!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c692d-147">[!code-cs[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="c692d-148">Los miembros estáticos se inicializan antes de que se obtenga acceso por primera vez al miembro estático y antes de que se llame al constructor estático, en caso de haberlo.</span><span class="sxs-lookup"><span data-stu-id="c692d-148">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="c692d-149">Para tener acceso a un miembro de clase estática, use el nombre de la clase en lugar de un nombre de variable para especificar la ubicación del miembro, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c692d-149">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 <span data-ttu-id="c692d-150">[!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c692d-150">[!code-cs[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="c692d-151">Si la clase contiene campos estáticos, proporcione un constructor estático que los inicialice al cargar la clase.</span><span class="sxs-lookup"><span data-stu-id="c692d-151">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="c692d-152">Una llamada a un método estático genera una instrucción de llamada en Lenguaje Intermedio de Microsoft (MSIL), mientras que una llamada a un método de instancia genera una instrucción `callvirt`, que también comprueba si hay referencias a un objeto NULL,</span><span class="sxs-lookup"><span data-stu-id="c692d-152">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="c692d-153">pero la mayoría de las veces la diferencia de rendimiento entre las dos no es significativo.</span><span class="sxs-lookup"><span data-stu-id="c692d-153">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c692d-154">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c692d-154">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c692d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="c692d-155">See Also</span></span>  
 <span data-ttu-id="c692d-156">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c692d-156">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c692d-157">[static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="c692d-157">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 <span data-ttu-id="c692d-158">[Clases](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="c692d-158">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="c692d-159">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="c692d-159">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="c692d-160">[Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="c692d-160">[Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) </span></span>  
 [<span data-ttu-id="c692d-161">Constructores de instancias</span><span class="sxs-lookup"><span data-stu-id="c692d-161">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)


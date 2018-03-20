---
title: "Tipos de puntero (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="57b47-102">Tipos de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="57b47-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="57b47-103">En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="57b47-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="57b47-104">Una declaración de tipos de puntero toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="57b47-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="57b47-105">Cualquiera de los tipos siguientes puede ser un tipo de puntero:</span><span class="sxs-lookup"><span data-stu-id="57b47-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="57b47-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) o [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="57b47-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="57b47-107">Cualquier tipo [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="57b47-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="57b47-108">Cualquier tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="57b47-109">Cualquier tipo struct definido por el usuario que solo contenga campos de tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="57b47-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="57b47-110">Los tipos de puntero no heredan de [object](../../../csharp/language-reference/keywords/object.md) y no existe ninguna conversión entre tipos de puntero y `object`.</span><span class="sxs-lookup"><span data-stu-id="57b47-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="57b47-111">Además, las conversiones boxing y unboxing no admiten punteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="57b47-112">Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="57b47-113">Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (\*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-113">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="57b47-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="57b47-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="57b47-115">Un puntero no puede señalar a una referencia ni a un [struct](../../../csharp/language-reference/keywords/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale.</span><span class="sxs-lookup"><span data-stu-id="57b47-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="57b47-116">El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="57b47-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="57b47-117">El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="57b47-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="57b47-118">A continuación se muestran ejemplos de declaraciones de tipos de puntero:</span><span class="sxs-lookup"><span data-stu-id="57b47-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="57b47-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57b47-119">Example</span></span>|<span data-ttu-id="57b47-120">Description</span><span class="sxs-lookup"><span data-stu-id="57b47-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="57b47-121">`p` es un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="57b47-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="57b47-122">`p` es un puntero a un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="57b47-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="57b47-123">`p` es una matriz unidimensional de punteros a enteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="57b47-124">`p` es un puntero a un valor char.</span><span class="sxs-lookup"><span data-stu-id="57b47-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="57b47-125">`p` es un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="57b47-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="57b47-126">El operador de direccionamiento indirecto del puntero \* puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-126">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="57b47-127">Por ejemplo, consideremos la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="57b47-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="57b47-128">La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="57b47-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="57b47-129">Hay varios ejemplos de punteros en los temas [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) (fixed [Instrucción, Referencia de C#])y [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) (Conversiones de puntero [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="57b47-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="57b47-130">En el ejemplo siguiente se muestra la necesidad de la palabra clave `unsafe` y la instrucción `fixed`, además de cómo incrementar un puntero interior.</span><span class="sxs-lookup"><span data-stu-id="57b47-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="57b47-131">Puede pegar este código en la función Main de una aplicación de consola para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="57b47-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="57b47-132">(Recuerde habilitar el código no seguro en el **Diseñador de proyectos**; elija **Proyecto** y **Propiedades** en la barra de menús y luego seleccione **Permitir código no seguro** en la pestaña **Compilar**).</span><span class="sxs-lookup"><span data-stu-id="57b47-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="57b47-133">No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="57b47-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="57b47-134">Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.</span><span class="sxs-lookup"><span data-stu-id="57b47-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="57b47-135">Un puntero puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="57b47-135">A pointer can be `null`.</span></span> <span data-ttu-id="57b47-136">La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.</span><span class="sxs-lookup"><span data-stu-id="57b47-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="57b47-137">Tenga en cuenta que pasar punteros entre métodos puede provocar un comportamiento no definido.</span><span class="sxs-lookup"><span data-stu-id="57b47-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="57b47-138">Valore la posibilidad de utilizar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función.</span><span class="sxs-lookup"><span data-stu-id="57b47-138">Consider a method that returns a pointer to a local variable through an `in`, `out` or `ref` parameter or as the function result.</span></span> <span data-ttu-id="57b47-139">Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.</span><span class="sxs-lookup"><span data-stu-id="57b47-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="57b47-140">En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:</span><span class="sxs-lookup"><span data-stu-id="57b47-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="57b47-141">Operador/Instrucción</span><span class="sxs-lookup"><span data-stu-id="57b47-141">Operator/Statement</span></span>|<span data-ttu-id="57b47-142">Usar</span><span class="sxs-lookup"><span data-stu-id="57b47-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="57b47-143">Realiza el direccionamiento indirecto del puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="57b47-144">Obtiene acceso a un miembro de un struct a través de un puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="57b47-145">[]</span><span class="sxs-lookup"><span data-stu-id="57b47-145">[]</span></span>|<span data-ttu-id="57b47-146">Indiza un puntero.</span><span class="sxs-lookup"><span data-stu-id="57b47-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="57b47-147">Obtiene la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="57b47-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="57b47-148">++ y --</span><span class="sxs-lookup"><span data-stu-id="57b47-148">++ and --</span></span>|<span data-ttu-id="57b47-149">Incrementa y disminuye los punteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="57b47-150">+ y -</span><span class="sxs-lookup"><span data-stu-id="57b47-150">+ and -</span></span>|<span data-ttu-id="57b47-151">Realiza aritmética con punteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="57b47-152">==, !=, \<, >, \<= y >=</span><span class="sxs-lookup"><span data-stu-id="57b47-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="57b47-153">Compara los punteros.</span><span class="sxs-lookup"><span data-stu-id="57b47-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="57b47-154">Asigna memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="57b47-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="57b47-155">Instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="57b47-155">`fixed` statement</span></span>|<span data-ttu-id="57b47-156">Fija provisionalmente una variable para que pueda encontrarse su dirección.</span><span class="sxs-lookup"><span data-stu-id="57b47-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="57b47-157">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="57b47-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="57b47-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="57b47-158">See Also</span></span>  
 [<span data-ttu-id="57b47-159">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="57b47-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="57b47-160">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="57b47-160">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="57b47-161">Conversiones de puntero</span><span class="sxs-lookup"><span data-stu-id="57b47-161">Pointer Conversions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [<span data-ttu-id="57b47-162">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="57b47-162">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="57b47-163">Tipos</span><span class="sxs-lookup"><span data-stu-id="57b47-163">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="57b47-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="57b47-164">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="57b47-165">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="57b47-165">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="57b47-166">stackalloc</span><span class="sxs-lookup"><span data-stu-id="57b47-166">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="57b47-167">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="57b47-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

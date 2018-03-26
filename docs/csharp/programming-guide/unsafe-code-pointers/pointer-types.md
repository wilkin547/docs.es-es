---
title: Tipos de puntero (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2018
---
# <a name="pointer-types-c-programming-guide"></a>Tipos de puntero (Guía de programación de C#)
En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia. Una declaración de tipos de puntero toma una de las siguientes formas:  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 Cualquiera de los tipos siguientes puede ser un tipo de puntero:  
  
-   [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) o [bool](../../../csharp/language-reference/keywords/bool.md).  
  
-   Cualquier tipo [enum](../../../csharp/language-reference/keywords/enum.md).  
  
-   Cualquier tipo de puntero.  
  
-   Cualquier tipo struct definido por el usuario que solo contenga campos de tipos no administrados.  
  
 Los tipos de puntero no heredan de [object](../../../csharp/language-reference/keywords/object.md) y no existe ninguna conversión entre tipos de puntero y `object`. Además, las conversiones boxing y unboxing no admiten punteros. Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.  
  
 Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero. Por ejemplo:  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 Un puntero no puede señalar a una referencia ni a un [struct](../../../csharp/language-reference/keywords/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale. El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.  
  
 El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`. A continuación se muestran ejemplos de declaraciones de tipos de puntero:  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`int* p`|`p` es un puntero a un entero.|  
|`int** p`|`p` es un puntero a un puntero a un entero.|  
|`int*[] p`|`p` es una matriz unidimensional de punteros a enteros.|  
|`char* p`|`p` es un puntero a un valor char.|  
|`void* p`|`p` es un puntero a un tipo desconocido.|  
  
 El operador de direccionamiento indirecto del puntero * puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero. Por ejemplo, consideremos la siguiente declaración:  
  
```  
int* myVariable;  
```  
  
 La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.  
  
 Hay varios ejemplos de punteros en los temas [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) (fixed [Instrucción, Referencia de C#])y [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) (Conversiones de puntero [Guía de programación de C#]).  En el ejemplo siguiente se muestra la necesidad de la palabra clave `unsafe` y la instrucción `fixed`, además de cómo incrementar un puntero interior.  Puede pegar este código en la función Main de una aplicación de consola para ejecutarla. (Recuerde habilitar el código no seguro en el **Diseñador de proyectos**; elija **Proyecto** y **Propiedades** en la barra de menús y luego seleccione **Permitir código no seguro** en la pestaña **Compilar**).  
  
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
  
 No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`. Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.  
  
 Un puntero puede ser `null`. La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.  
  
 Tenga en cuenta que pasar punteros entre métodos puede provocar un comportamiento no definido. Valore la posibilidad de utilizar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función. Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.  
  
 En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:  
  
|Operador/Instrucción|Usar|  
|-------------------------|---------|  
|*|Realiza el direccionamiento indirecto del puntero.|  
|->|Obtiene acceso a un miembro de un struct a través de un puntero.|  
|[]|Indiza un puntero.|  
|`&`|Obtiene la dirección de una variable.|  
|++ y --|Incrementa y disminuye los punteros.|  
|+ y -|Realiza aritmética con punteros.|  
|==, !=, \<, >, \<= y >=|Compara los punteros.|  
|`stackalloc`|Asigna memoria en la pila.|  
|Instrucción `fixed`|Fija provisionalmente una variable para que pueda encontrarse su dirección.|  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Conversiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)  
 [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

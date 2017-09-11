---
title: "Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
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
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="2e37e-102">Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2e37e-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="2e37e-103">El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: `true`, `false` y `null`.</span><span class="sxs-lookup"><span data-stu-id="2e37e-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="2e37e-104">Por lo tanto, el tipo `bool?` no se puede usar en instrucciones condicionales como `if`, `for` o `while`.</span><span class="sxs-lookup"><span data-stu-id="2e37e-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="2e37e-105">Por ejemplo, el siguiente código causa un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="2e37e-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="2e37e-106">Esto no está permitido porque no está claro lo que `null` significa en el contexto de una instrucción condicional.</span><span class="sxs-lookup"><span data-stu-id="2e37e-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="2e37e-107">Para usar un tipo `bool?` en una instrucción condicional, compruebe antes su propiedad <xref:System.Nullable%601.HasValue%2A> para asegurarse de que el valor no sea `null` y, después, conviértalo a `bool`.</span><span class="sxs-lookup"><span data-stu-id="2e37e-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="2e37e-108">Para obtener más información, vea [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="2e37e-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="2e37e-109">Si realiza la conversión en un `bool?` con un valor `null`, se producirá una excepción <xref:System.InvalidOperationException> en la prueba condicional.</span><span class="sxs-lookup"><span data-stu-id="2e37e-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="2e37e-110">En el siguiente ejemplo se muestra una forma de conversión segura de `bool?` a `bool`:</span><span class="sxs-lookup"><span data-stu-id="2e37e-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e37e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e37e-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e37e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e37e-112">See Also</span></span>  
 <span data-ttu-id="2e37e-113">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e37e-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2e37e-114">[Palabras clave de literales](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="2e37e-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="2e37e-115">[Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e37e-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="2e37e-116">Operador !</span><span class="sxs-lookup"><span data-stu-id="2e37e-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)


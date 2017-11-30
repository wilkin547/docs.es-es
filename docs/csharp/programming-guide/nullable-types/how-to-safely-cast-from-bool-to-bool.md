---
title: "Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a6fa65c15bb5f1da9960dbc17bd25b4087ab862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="51683-102">Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="51683-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="51683-103">El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: `true`, `false` y `null`.</span><span class="sxs-lookup"><span data-stu-id="51683-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="51683-104">Por lo tanto, el tipo `bool?` no se puede usar en instrucciones condicionales como `if`, `for` o `while`.</span><span class="sxs-lookup"><span data-stu-id="51683-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="51683-105">Por ejemplo, el siguiente código causa un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="51683-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="51683-106">Esto no está permitido porque no está claro lo que `null` significa en el contexto de una instrucción condicional.</span><span class="sxs-lookup"><span data-stu-id="51683-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="51683-107">Para usar un tipo `bool?` en una instrucción condicional, compruebe antes su propiedad <xref:System.Nullable%601.HasValue%2A> para asegurarse de que el valor no sea `null` y, después, conviértalo a `bool`.</span><span class="sxs-lookup"><span data-stu-id="51683-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="51683-108">Para obtener más información, vea [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="51683-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="51683-109">Si realiza la conversión en un `bool?` con un valor `null`, se producirá una excepción <xref:System.InvalidOperationException> en la prueba condicional.</span><span class="sxs-lookup"><span data-stu-id="51683-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="51683-110">En el siguiente ejemplo se muestra una forma de conversión segura de `bool?` a `bool`:</span><span class="sxs-lookup"><span data-stu-id="51683-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="51683-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51683-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51683-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="51683-112">See Also</span></span>  
 [<span data-ttu-id="51683-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="51683-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="51683-114">Palabras clave de literales</span><span class="sxs-lookup"><span data-stu-id="51683-114">Literal Keywords</span></span>](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [<span data-ttu-id="51683-115">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="51683-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="51683-116">Operador !</span><span class="sxs-lookup"><span data-stu-id="51683-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

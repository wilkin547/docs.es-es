---
title: 'Cómo: Utilizar la sobrecarga de operadores para crear una clase de números complejos (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
ms.openlocfilehash: d746355dac1b99690a5a94c829bd35598c6c8be8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328869"
---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="60466-102">Cómo: Utilizar la sobrecarga de operadores para crear una clase de números complejos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="60466-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="60466-103">En este ejemplo, se muestra cómo puede usar la sobrecarga de operador para crear una clase de números complejos `Complex` que define la suma compleja.</span><span class="sxs-lookup"><span data-stu-id="60466-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="60466-104">El programa muestra el imaginario y las partes reales de los números y el resultado de la suma con una invalidación del método `ToString`.</span><span class="sxs-lookup"><span data-stu-id="60466-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60466-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60466-105">Example</span></span>  
 [!code-csharp[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="60466-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="60466-106">See Also</span></span>  
 [<span data-ttu-id="60466-107">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="60466-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="60466-108">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="60466-108">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="60466-109">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="60466-109">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 <span data-ttu-id="60466-110">[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (¿Por qué los operadores sobrecargados son siempre estáticos en C#?)</span><span class="sxs-lookup"><span data-stu-id="60466-110">[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)</span></span>

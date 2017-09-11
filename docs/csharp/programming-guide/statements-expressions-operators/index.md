---
title: "Instrucciones, expresiones y operadores (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
caps.latest.revision: 22
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="84b8e-102">Instrucciones, expresiones y operadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="84b8e-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="84b8e-103">El código de C# que conforma una aplicación consta de instrucciones basadas en palabras clave, expresiones y operadores.</span><span class="sxs-lookup"><span data-stu-id="84b8e-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="84b8e-104">Esta sección contiene información sobre los elementos fundamentales de un programa de C#.</span><span class="sxs-lookup"><span data-stu-id="84b8e-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="84b8e-105">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="84b8e-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="84b8e-106">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="84b8e-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="84b8e-107">Expresiones</span><span class="sxs-lookup"><span data-stu-id="84b8e-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="84b8e-108">Miembros con forma de expresión</span><span class="sxs-lookup"><span data-stu-id="84b8e-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="84b8e-109">Operadores</span><span class="sxs-lookup"><span data-stu-id="84b8e-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="84b8e-110">Funciones anónimas</span><span class="sxs-lookup"><span data-stu-id="84b8e-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="84b8e-111">Operadores sobrecargables</span><span class="sxs-lookup"><span data-stu-id="84b8e-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="84b8e-112">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="84b8e-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="84b8e-113">Utilizar operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="84b8e-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="84b8e-114">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="84b8e-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="84b8e-115">Cómo: Utilizar la sobrecarga de operadores para crear una clase de números complejos</span><span class="sxs-lookup"><span data-stu-id="84b8e-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="84b8e-116">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="84b8e-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="84b8e-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="84b8e-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84b8e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="84b8e-118">See Also</span></span>  
 <span data-ttu-id="84b8e-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="84b8e-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="84b8e-120">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="84b8e-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)


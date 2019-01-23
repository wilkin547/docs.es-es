---
title: 'Operadores de conversión: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 927640b63773d24be93cc90427668f9568a39652
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362735"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="41149-102">Operadores de conversión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="41149-102">Conversion operators (C# Programming Guide)</span></span>

<span data-ttu-id="41149-103">C# permite a los programadores declarar conversiones en clases o structs, de manera que las clases o structs puedan convertirse a o desde otras clases o structs, o tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="41149-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="41149-104">Las conversiones se definen como los operadores y se denominan por el tipo al que se convierten.</span><span class="sxs-lookup"><span data-stu-id="41149-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="41149-105">El tipo del argumento que se va a convertir o el tipo del resultado de la conversión, pero no ambos, debe ser el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="41149-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="41149-106">Información general sobre operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="41149-106">Conversion operators overview</span></span>

 <span data-ttu-id="41149-107">Los operadores de conversión tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="41149-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="41149-108">Las conversiones declaradas como `implicit` se producen automáticamente cuando se necesita.</span><span class="sxs-lookup"><span data-stu-id="41149-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="41149-109">Las conversiones declaradas como `explicit` necesitan que se llame a una conversión.</span><span class="sxs-lookup"><span data-stu-id="41149-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="41149-110">Todas las conversiones se deben declarar como `static`.</span><span class="sxs-lookup"><span data-stu-id="41149-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="41149-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="41149-111">Related sections</span></span>

 <span data-ttu-id="41149-112">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="41149-112">For more information:</span></span>  
  
-   [<span data-ttu-id="41149-113">Utilizar operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="41149-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="41149-114">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="41149-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="41149-115">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="41149-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="41149-116">explicit</span><span class="sxs-lookup"><span data-stu-id="41149-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="41149-117">implicit</span><span class="sxs-lookup"><span data-stu-id="41149-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="41149-118">static</span><span class="sxs-lookup"><span data-stu-id="41149-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="41149-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="41149-119">See also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="41149-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="41149-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- <span data-ttu-id="41149-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="41149-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>

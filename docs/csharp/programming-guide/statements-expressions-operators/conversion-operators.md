---
title: "Operadores de conversión (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5277c1160c604ee56ff575df5bd603e115588d21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="cf759-102">Operadores de conversión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cf759-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="cf759-103">C# permite a los programadores declarar conversiones en clases o structs, de manera que las clases o structs puedan convertirse a o desde otras clases o structs, o tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="cf759-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="cf759-104">Las conversiones se definen como los operadores y se denominan por el tipo al que se convierten.</span><span class="sxs-lookup"><span data-stu-id="cf759-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="cf759-105">El tipo del argumento que se va a convertir o el tipo del resultado de la conversión, pero no ambos, debe ser el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="cf759-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="cf759-106">Información general sobre operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="cf759-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="cf759-107">Los operadores de conversión tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf759-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="cf759-108">Las conversiones declaradas como `implicit` se producen automáticamente cuando se necesita.</span><span class="sxs-lookup"><span data-stu-id="cf759-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="cf759-109">Las conversiones declaradas como `explicit` necesitan que se llame a una conversión.</span><span class="sxs-lookup"><span data-stu-id="cf759-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="cf759-110">Todas las conversiones se deben declarar como `static`.</span><span class="sxs-lookup"><span data-stu-id="cf759-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf759-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cf759-111">Related Sections</span></span>  
 <span data-ttu-id="cf759-112">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="cf759-112">For more information:</span></span>  
  
-   [<span data-ttu-id="cf759-113">Utilizar operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="cf759-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="cf759-114">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="cf759-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="cf759-115">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="cf759-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="cf759-116">explicit</span><span class="sxs-lookup"><span data-stu-id="cf759-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="cf759-117">implicit</span><span class="sxs-lookup"><span data-stu-id="cf759-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="cf759-118">static</span><span class="sxs-lookup"><span data-stu-id="cf759-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf759-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf759-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="cf759-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cf759-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="cf759-121">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="cf759-121">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>

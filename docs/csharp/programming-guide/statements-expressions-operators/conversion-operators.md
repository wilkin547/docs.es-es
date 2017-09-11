---
title: "Operadores de conversión (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="fc60c-102">Operadores de conversión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fc60c-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="fc60c-103">C# permite a los programadores declarar conversiones en clases o structs, de manera que las clases o structs puedan convertirse a o desde otras clases o structs, o tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="fc60c-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="fc60c-104">Las conversiones se definen como los operadores y se denominan por el tipo al que se convierten.</span><span class="sxs-lookup"><span data-stu-id="fc60c-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="fc60c-105">El tipo del argumento que se va a convertir o el tipo del resultado de la conversión, pero no ambos, debe ser el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="fc60c-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 <span data-ttu-id="fc60c-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc60c-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span></span>  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="fc60c-107">Información general sobre operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="fc60c-107">Conversion Operators Overview</span></span>  
 <span data-ttu-id="fc60c-108">Los operadores de conversión tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc60c-108">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="fc60c-109">Las conversiones declaradas como `implicit` se producen automáticamente cuando se necesita.</span><span class="sxs-lookup"><span data-stu-id="fc60c-109">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="fc60c-110">Las conversiones declaradas como `explicit` necesitan que se llame a una conversión.</span><span class="sxs-lookup"><span data-stu-id="fc60c-110">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="fc60c-111">Todas las conversiones se deben declarar como `static`.</span><span class="sxs-lookup"><span data-stu-id="fc60c-111">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fc60c-112">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="fc60c-112">Related Sections</span></span>  
 <span data-ttu-id="fc60c-113">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="fc60c-113">For more information:</span></span>  
  
-   [<span data-ttu-id="fc60c-114">Utilizar operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="fc60c-114">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="fc60c-115">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="fc60c-115">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="fc60c-116">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="fc60c-116">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="fc60c-117">explicit</span><span class="sxs-lookup"><span data-stu-id="fc60c-117">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="fc60c-118">implicit</span><span class="sxs-lookup"><span data-stu-id="fc60c-118">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="fc60c-119">static</span><span class="sxs-lookup"><span data-stu-id="fc60c-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc60c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc60c-120">See Also</span></span>  
 <span data-ttu-id="fc60c-121"><xref:System.Convert></span><span class="sxs-lookup"><span data-stu-id="fc60c-121"><xref:System.Convert></span></span>   
 <span data-ttu-id="fc60c-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc60c-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fc60c-123">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="fc60c-123">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>


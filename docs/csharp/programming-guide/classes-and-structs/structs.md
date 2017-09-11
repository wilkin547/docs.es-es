---
title: "Structs (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="e99ec-102">Structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e99ec-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="e99ec-103">Los structs se definen mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md), por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e99ec-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="e99ec-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e99ec-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="e99ec-105">Los structs comparten la mayoría de la sintaxis con las clases, aunque están más limitados que estas:</span><span class="sxs-lookup"><span data-stu-id="e99ec-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="e99ec-106">Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.</span><span class="sxs-lookup"><span data-stu-id="e99ec-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="e99ec-107">Un struct no puede declarar un constructor predeterminado (un constructor sin parámetros) ni un finalizador.</span><span class="sxs-lookup"><span data-stu-id="e99ec-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="e99ec-108">Los structs se copian en la asignación.</span><span class="sxs-lookup"><span data-stu-id="e99ec-108">Structs are copied on assignment.</span></span> <span data-ttu-id="e99ec-109">Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original.</span><span class="sxs-lookup"><span data-stu-id="e99ec-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="e99ec-110">Es importante que lo recuerde al trabajar con colecciones de tipos de valor como Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="e99ec-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="e99ec-111">Los structs son tipos de valor y las clases son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="e99ec-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="e99ec-112">A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.</span><span class="sxs-lookup"><span data-stu-id="e99ec-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="e99ec-113">Los structs pueden declarar constructores que tengan parámetros.</span><span class="sxs-lookup"><span data-stu-id="e99ec-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="e99ec-114">Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase.</span><span class="sxs-lookup"><span data-stu-id="e99ec-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="e99ec-115">Todos los structs heredan directamente de `System.ValueType`, que hereda de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="e99ec-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="e99ec-116">Un struct puede implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="e99ec-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="e99ec-117">Un struct se puede usar como un tipo que acepta valores NULL y se le puede asignar un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="e99ec-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e99ec-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e99ec-118">Related Sections</span></span>  
 <span data-ttu-id="e99ec-119">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="e99ec-119">For more information:</span></span>  
  
-   [<span data-ttu-id="e99ec-120">Utilizar estructuras</span><span class="sxs-lookup"><span data-stu-id="e99ec-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="e99ec-121">Constructores</span><span class="sxs-lookup"><span data-stu-id="e99ec-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="e99ec-122">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="e99ec-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="e99ec-123">Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase</span><span class="sxs-lookup"><span data-stu-id="e99ec-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="e99ec-124">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="e99ec-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="e99ec-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99ec-125">See Also</span></span>  
 <span data-ttu-id="e99ec-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e99ec-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e99ec-127">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="e99ec-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="e99ec-128">Clases</span><span class="sxs-lookup"><span data-stu-id="e99ec-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)


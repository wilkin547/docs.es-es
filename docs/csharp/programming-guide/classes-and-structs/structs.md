---
title: Structs (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322993"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="0b491-102">Structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0b491-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="0b491-103">Los structs se definen mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md), por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0b491-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="0b491-104">Los structs comparten la mayoría de la sintaxis con las clases, aunque están más limitados que estas:</span><span class="sxs-lookup"><span data-stu-id="0b491-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="0b491-105">Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.</span><span class="sxs-lookup"><span data-stu-id="0b491-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="0b491-106">Un struct no puede declarar un constructor predeterminado (un constructor sin parámetros) ni un finalizador.</span><span class="sxs-lookup"><span data-stu-id="0b491-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="0b491-107">Los structs se copian en la asignación.</span><span class="sxs-lookup"><span data-stu-id="0b491-107">Structs are copied on assignment.</span></span> <span data-ttu-id="0b491-108">Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original.</span><span class="sxs-lookup"><span data-stu-id="0b491-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="0b491-109">Es importante que lo recuerde al trabajar con colecciones de tipos de valor como Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="0b491-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="0b491-110">Los structs son tipos de valor y las clases son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0b491-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="0b491-111">A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.</span><span class="sxs-lookup"><span data-stu-id="0b491-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="0b491-112">Los structs pueden declarar constructores que tengan parámetros.</span><span class="sxs-lookup"><span data-stu-id="0b491-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="0b491-113">Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase.</span><span class="sxs-lookup"><span data-stu-id="0b491-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="0b491-114">Todos los structs heredan directamente de `System.ValueType`, que hereda de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="0b491-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="0b491-115">Un struct puede implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="0b491-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="0b491-116">Un struct se puede usar como un tipo que acepta valores NULL y se le puede asignar un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="0b491-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0b491-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0b491-117">Related Sections</span></span>  
 <span data-ttu-id="0b491-118">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="0b491-118">For more information:</span></span>  
  
-   [<span data-ttu-id="0b491-119">Utilizar estructuras</span><span class="sxs-lookup"><span data-stu-id="0b491-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="0b491-120">Constructores</span><span class="sxs-lookup"><span data-stu-id="0b491-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="0b491-121">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="0b491-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="0b491-122">Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase</span><span class="sxs-lookup"><span data-stu-id="0b491-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="0b491-123">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="0b491-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="0b491-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b491-124">See Also</span></span>  
 [<span data-ttu-id="0b491-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0b491-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0b491-126">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="0b491-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="0b491-127">Clases</span><span class="sxs-lookup"><span data-stu-id="0b491-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

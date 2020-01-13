---
title: 'Structs: Guía de programación de C#'
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 5150ff2d6edde0ac91bc6548fd499b76af614007
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705423"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="cc93c-102">Structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cc93c-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="cc93c-103">Los structs se definen mediante la palabra clave [struct](../../language-reference/keywords/struct.md), por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc93c-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="cc93c-104">Los structs comparten la mayor parte de la sintaxis de las clases.</span><span class="sxs-lookup"><span data-stu-id="cc93c-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="cc93c-105">El nombre de la estructura debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.</span><span class="sxs-lookup"><span data-stu-id="cc93c-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="cc93c-106">Los structs son más limitados que las clases en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc93c-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="cc93c-107">Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.</span><span class="sxs-lookup"><span data-stu-id="cc93c-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="cc93c-108">Un struct no puede declarar un constructor sin parámetros ni un finalizador.</span><span class="sxs-lookup"><span data-stu-id="cc93c-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="cc93c-109">Los structs se copian en la asignación.</span><span class="sxs-lookup"><span data-stu-id="cc93c-109">Structs are copied on assignment.</span></span> <span data-ttu-id="cc93c-110">Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original.</span><span class="sxs-lookup"><span data-stu-id="cc93c-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="cc93c-111">Es importante que lo recuerde al trabajar con colecciones de tipos de valor como `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="cc93c-112">Los structs son tipos de valor, a diferencia de las clases, que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="cc93c-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="cc93c-113">A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="cc93c-114">Los structs pueden declarar constructores que tengan parámetros.</span><span class="sxs-lookup"><span data-stu-id="cc93c-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="cc93c-115">Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase.</span><span class="sxs-lookup"><span data-stu-id="cc93c-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="cc93c-116">Todos los structs heredan directamente de <xref:System.ValueType>, que hereda de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cc93c-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="cc93c-117">Un struct puede implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="cc93c-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="cc93c-118">Una estructura no puede ser `null` y a una variable de estructura no se le puede asignar `null` a menos que la variable se declare como tipo de valor que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cc93c-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable value type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc93c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc93c-119">See also</span></span>

- [<span data-ttu-id="cc93c-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cc93c-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cc93c-121">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="cc93c-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="cc93c-122">Clases</span><span class="sxs-lookup"><span data-stu-id="cc93c-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="cc93c-123">Tipos de valores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="cc93c-123">Nullable value types</span></span>](../../language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="cc93c-124">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="cc93c-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="cc93c-125">Utilizar estructuras</span><span class="sxs-lookup"><span data-stu-id="cc93c-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="cc93c-126">Procedimiento para saber las diferencias entre pasar a un método un struct y una referencia a clase</span><span class="sxs-lookup"><span data-stu-id="cc93c-126">How to know the difference between passing a struct and passing a class reference to a method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)

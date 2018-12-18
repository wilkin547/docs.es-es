---
title: 'Structs: Guía de programación de C#'
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 3f19d0485939e1923c479c1c9fdeb06572a11e14
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240390"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="1fc8b-102">Structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1fc8b-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="1fc8b-103">Los structs se definen mediante la palabra clave [struct](../../language-reference/keywords/struct.md), por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1fc8b-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
<span data-ttu-id="1fc8b-104">Los structs comparten la mayor parte de la sintaxis de las clases.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="1fc8b-105">El nombre de la estructura debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="1fc8b-106">Los structs son más limitados que las clases en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1fc8b-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="1fc8b-107">Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="1fc8b-108">Un struct no puede declarar un constructor predeterminado (un constructor sin parámetros) ni un finalizador.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="1fc8b-109">Los structs se copian en la asignación.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-109">Structs are copied on assignment.</span></span> <span data-ttu-id="1fc8b-110">Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="1fc8b-111">Es importante que lo recuerde al trabajar con colecciones de tipos de valor como `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="1fc8b-112">Los structs son tipos de valor, a diferencia de las clases, que son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="1fc8b-113">A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="1fc8b-114">Los structs pueden declarar constructores que tengan parámetros.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="1fc8b-115">Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="1fc8b-116">Todos los structs heredan directamente de <xref:System.ValueType>, que hereda de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="1fc8b-117">Un struct puede implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-117">A struct can implement interfaces.</span></span>  
- <span data-ttu-id="1fc8b-118">Un struct se puede usar como un tipo que acepta valores NULL y se le puede asignar un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="1fc8b-118">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1fc8b-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1fc8b-119">Related sections</span></span>  

<span data-ttu-id="1fc8b-120">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="1fc8b-120">For more information:</span></span>  
  
- [<span data-ttu-id="1fc8b-121">Utilizar estructuras</span><span class="sxs-lookup"><span data-stu-id="1fc8b-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="1fc8b-122">Constructores</span><span class="sxs-lookup"><span data-stu-id="1fc8b-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="1fc8b-123">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="1fc8b-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="1fc8b-124">Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase</span><span class="sxs-lookup"><span data-stu-id="1fc8b-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="1fc8b-125">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="1fc8b-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="1fc8b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fc8b-126">See also</span></span>

- [<span data-ttu-id="1fc8b-127">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1fc8b-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1fc8b-128">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="1fc8b-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="1fc8b-129">Clases</span><span class="sxs-lookup"><span data-stu-id="1fc8b-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="1fc8b-130">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="1fc8b-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)

---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 05b1e6b646c519216eba2d4f0df7a3e32f3dafbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661257"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="5c01c-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c01c-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="5c01c-103">Especifica que una clase puede usarse únicamente como clase base y que no se puede crear un objeto directamente a partir de él.</span><span class="sxs-lookup"><span data-stu-id="5c01c-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c01c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c01c-104">Remarks</span></span>  
 <span data-ttu-id="5c01c-105">El propósito de un *clase base* (también conocido como un *clase abstracta*) consiste en definir la funcionalidad común a todas las clases que derivan de ella.</span><span class="sxs-lookup"><span data-stu-id="5c01c-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="5c01c-106">Esto evita que las clases derivadas tener que volver a definir los elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="5c01c-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="5c01c-107">En algunos casos, esta funcionalidad común no es lo suficientemente completa para crear un objeto utilizable y cada clase derivada define la funcionalidad que falta.</span><span class="sxs-lookup"><span data-stu-id="5c01c-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="5c01c-108">En tal caso, desea que el código usado para crear objetos solo desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="5c01c-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="5c01c-109">Usa `MustInherit` en la clase base para exigir esto.</span><span class="sxs-lookup"><span data-stu-id="5c01c-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="5c01c-110">Otro uso de un `MustInherit` clase consiste en restringir una variable a un conjunto de clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5c01c-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="5c01c-111">Puede definir una clase base y derivar todas estas clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5c01c-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="5c01c-112">La clase base no es necesario proporcionar una funcionalidad común a todas las clases derivadas, pero puede servir como un filtro para asignar valores a variables.</span><span class="sxs-lookup"><span data-stu-id="5c01c-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="5c01c-113">Si el código utilizado declara una variable como la clase base, Visual Basic permite asignar solo un objeto de una de las clases derivadas a esa variable.</span><span class="sxs-lookup"><span data-stu-id="5c01c-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="5c01c-114">.NET Framework define varios `MustInherit` clases, entre ellos <xref:System.Array>, <xref:System.Enum>, y <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="5c01c-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="5c01c-115"><xref:System.ValueType> es un ejemplo de una clase base que restringe una variable.</span><span class="sxs-lookup"><span data-stu-id="5c01c-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="5c01c-116">Todos los tipos de valor derivan de <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="5c01c-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="5c01c-117">Si declara una variable como <xref:System.ValueType>, puede asignar solo los tipos de valor a esa variable.</span><span class="sxs-lookup"><span data-stu-id="5c01c-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5c01c-118">Reglas</span><span class="sxs-lookup"><span data-stu-id="5c01c-118">Rules</span></span>  
  
- <span data-ttu-id="5c01c-119">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="5c01c-119">**Declaration Context.**</span></span> <span data-ttu-id="5c01c-120">Puede usar `MustInherit` únicamente en un `Class` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c01c-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="5c01c-121">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="5c01c-121">**Combined Modifiers.**</span></span> <span data-ttu-id="5c01c-122">No puede especificar `MustInherit` junto con `NotInheritable` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="5c01c-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c01c-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c01c-123">Example</span></span>  
 <span data-ttu-id="5c01c-124">El ejemplo siguiente muestra la herencia forzada y reemplazo forzado.</span><span class="sxs-lookup"><span data-stu-id="5c01c-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="5c01c-125">La clase base `shape` define una variable `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="5c01c-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="5c01c-126">Las clases `circle` y `square` derivan `shape`.</span><span class="sxs-lookup"><span data-stu-id="5c01c-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="5c01c-127">Heredan la definición de `acrossLine`, pero debe definir la función `area` porque ese cálculo es diferente para cada tipo de forma.</span><span class="sxs-lookup"><span data-stu-id="5c01c-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="5c01c-128">Puede declarar `shape1` y `shape2` a ser de tipo `shape`.</span><span class="sxs-lookup"><span data-stu-id="5c01c-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="5c01c-129">Sin embargo, no se puede crear un objeto de `shape` porque carece de la funcionalidad de la función `area` y se marca como `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="5c01c-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="5c01c-130">Dado que se declaran como `shape`, las variables `shape1` y `shape2` están restringidos a los objetos de las clases derivadas `circle` y `square`.</span><span class="sxs-lookup"><span data-stu-id="5c01c-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="5c01c-131">Visual Basic no permite asignar cualquier otro objeto a estas variables, lo que le ofrece un alto nivel de seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="5c01c-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="5c01c-132">Uso</span><span class="sxs-lookup"><span data-stu-id="5c01c-132">Usage</span></span>  
 <span data-ttu-id="5c01c-133">El `MustInherit` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="5c01c-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="5c01c-134">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5c01c-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c01c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c01c-135">See also</span></span>

- [<span data-ttu-id="5c01c-136">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5c01c-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="5c01c-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="5c01c-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="5c01c-138">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c01c-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="5c01c-139">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="5c01c-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

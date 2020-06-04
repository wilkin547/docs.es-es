---
title: MustInherit
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
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396212"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="c16ea-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c16ea-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="c16ea-103">Especifica que una clase se puede usar solo como una clase base y que no se puede crear un objeto directamente a partir de ella.</span><span class="sxs-lookup"><span data-stu-id="c16ea-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c16ea-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c16ea-104">Remarks</span></span>  
 <span data-ttu-id="c16ea-105">El propósito de una *clase base* (también conocida como *clase abstracta*) es definir la funcionalidad común a todas las clases derivadas de ella.</span><span class="sxs-lookup"><span data-stu-id="c16ea-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="c16ea-106">Esto evita que las clases derivadas tengan que volver a definir los elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="c16ea-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="c16ea-107">En algunos casos, esta funcionalidad común no es suficiente para crear un objeto utilizable y cada clase derivada define la funcionalidad que falta.</span><span class="sxs-lookup"><span data-stu-id="c16ea-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="c16ea-108">En tal caso, desea que el código utilizado solo cree objetos a partir de las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="c16ea-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="c16ea-109">Utilice `MustInherit` en la clase base para aplicar este.</span><span class="sxs-lookup"><span data-stu-id="c16ea-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="c16ea-110">Otro uso de una `MustInherit` clase es restringir una variable a un conjunto de clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c16ea-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="c16ea-111">Puede definir una clase base y derivar todas estas clases relacionadas de ella.</span><span class="sxs-lookup"><span data-stu-id="c16ea-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="c16ea-112">No es necesario que la clase base proporcione ninguna funcionalidad común a todas las clases derivadas, pero puede servir como filtro para asignar valores a variables.</span><span class="sxs-lookup"><span data-stu-id="c16ea-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="c16ea-113">Si el código utilizado declara una variable como la clase base, Visual Basic le permite asignar solo un objeto de una de las clases derivadas a esa variable.</span><span class="sxs-lookup"><span data-stu-id="c16ea-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="c16ea-114">El .NET Framework define varias `MustInherit` clases, entre ellas <xref:System.Array> , <xref:System.Enum> y <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="c16ea-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="c16ea-115"><xref:System.ValueType>es un ejemplo de una clase base que restringe una variable.</span><span class="sxs-lookup"><span data-stu-id="c16ea-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="c16ea-116">Todos los tipos de valor se derivan de <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="c16ea-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="c16ea-117">Si declara una variable como <xref:System.ValueType> , solo podrá asignar tipos de valor a esa variable.</span><span class="sxs-lookup"><span data-stu-id="c16ea-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c16ea-118">Reglas</span><span class="sxs-lookup"><span data-stu-id="c16ea-118">Rules</span></span>  
  
- <span data-ttu-id="c16ea-119">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="c16ea-119">**Declaration Context.**</span></span> <span data-ttu-id="c16ea-120">Solo se puede usar `MustInherit` en una `Class` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c16ea-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="c16ea-121">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="c16ea-121">**Combined Modifiers.**</span></span> <span data-ttu-id="c16ea-122">No se puede especificar `MustInherit` junto con `NotInheritable` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="c16ea-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c16ea-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c16ea-123">Example</span></span>  
 <span data-ttu-id="c16ea-124">En el ejemplo siguiente se muestra la herencia forzada y el reemplazo forzado.</span><span class="sxs-lookup"><span data-stu-id="c16ea-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="c16ea-125">La clase base `shape` define una variable `acrossLine` .</span><span class="sxs-lookup"><span data-stu-id="c16ea-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="c16ea-126">Las clases `circle` y `square` derivan de `shape` .</span><span class="sxs-lookup"><span data-stu-id="c16ea-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="c16ea-127">Heredan la definición de `acrossLine` , pero deben definir la función `area` porque ese cálculo es diferente para cada tipo de forma.</span><span class="sxs-lookup"><span data-stu-id="c16ea-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="c16ea-128">Puede declarar `shape1` y `shape2` para que sean de tipo `shape` .</span><span class="sxs-lookup"><span data-stu-id="c16ea-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="c16ea-129">Sin embargo, no se puede crear un objeto desde `shape` porque carece de la funcionalidad de la función `area` y está marcado como `MustInherit` .</span><span class="sxs-lookup"><span data-stu-id="c16ea-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="c16ea-130">Dado que se declaran como `shape` , las variables `shape1` y `shape2` están restringidas a los objetos de las clases derivadas `circle` y `square` .</span><span class="sxs-lookup"><span data-stu-id="c16ea-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="c16ea-131">Visual Basic no permite asignar ningún otro objeto a estas variables, lo que proporciona un alto nivel de seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="c16ea-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c16ea-132">Uso</span><span class="sxs-lookup"><span data-stu-id="c16ea-132">Usage</span></span>  
 <span data-ttu-id="c16ea-133">El `MustInherit` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="c16ea-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="c16ea-134">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="c16ea-134">Class Statement</span></span>](../statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c16ea-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c16ea-135">See also</span></span>

- [<span data-ttu-id="c16ea-136">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="c16ea-136">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="c16ea-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="c16ea-137">NotInheritable</span></span>](notinheritable.md)
- [<span data-ttu-id="c16ea-138">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c16ea-138">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="c16ea-139">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="c16ea-139">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

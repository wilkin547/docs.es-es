---
description: 'Más información acerca de: ReadOnly (Visual Basic)'
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: f510271531f6e6604f2b542d8331d1a1d7f64d58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700915"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="5dfbe-103">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5dfbe-103">ReadOnly (Visual Basic)</span></span>

<span data-ttu-id="5dfbe-104">Especifica que una variable o una propiedad se puede leer pero no escribir.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-104">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dfbe-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5dfbe-105">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="5dfbe-106">Reglas</span><span class="sxs-lookup"><span data-stu-id="5dfbe-106">Rules</span></span>

- <span data-ttu-id="5dfbe-107">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="5dfbe-107">**Declaration Context.**</span></span> <span data-ttu-id="5dfbe-108">Solo se puede usar `ReadOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-108">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="5dfbe-109">Esto significa que el contexto de la declaración de un `ReadOnly` elemento debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-109">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="5dfbe-110">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="5dfbe-110">**Combined Modifiers.**</span></span> <span data-ttu-id="5dfbe-111">No se puede especificar `ReadOnly` junto con `Static` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-111">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="5dfbe-112">**Asignación de un valor.**</span><span class="sxs-lookup"><span data-stu-id="5dfbe-112">**Assigning a Value.**</span></span> <span data-ttu-id="5dfbe-113">El código que consume una `ReadOnly` propiedad no puede establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-113">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="5dfbe-114">Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-114">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="5dfbe-115">Puede asignar un valor a una `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-115">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="5dfbe-116">Cuándo usar una variable de solo lectura</span><span class="sxs-lookup"><span data-stu-id="5dfbe-116">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="5dfbe-117">Hay situaciones en las que no se puede usar una [instrucción const](../statements/const-statement.md) para declarar y asignar un valor constante.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-117">There are situations in which you cannot use a [Const Statement](../statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="5dfbe-118">Por ejemplo, `Const` es posible que la instrucción no acepte el tipo de datos que desea asignar o que no pueda calcular el valor en tiempo de compilación con una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-118">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="5dfbe-119">Es posible que ni siquiera conozca el valor en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-119">You might not even know the value at compile time.</span></span> <span data-ttu-id="5dfbe-120">En estos casos, puede usar una `ReadOnly` variable para contener un valor constante.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-120">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dfbe-121">Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros aunque la propia variable sea `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="5dfbe-121">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="5dfbe-122">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5dfbe-122">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="5dfbe-123">Cuando se inicializa, la matriz a la que señala `characterArray()` contiene "x", "y" y "z".</span><span class="sxs-lookup"><span data-stu-id="5dfbe-123">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="5dfbe-124">Dado que la variable `characterArray` es `ReadOnly` , no se puede cambiar su valor una vez inicializado; es decir, no se puede asignar una nueva matriz a ella.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-124">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="5dfbe-125">Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-125">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="5dfbe-126">Después de una llamada al procedimiento `ChangeArrayElement` , la matriz a la que señala `characterArray()` contiene "x", "M" y "z".</span><span class="sxs-lookup"><span data-stu-id="5dfbe-126">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="5dfbe-127">Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](byval.md), lo que evita que el procedimiento cambie el argumento de llamada en sí, pero permite cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-127">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="5dfbe-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dfbe-128">Example</span></span>

<span data-ttu-id="5dfbe-129">En el ejemplo siguiente se define una `ReadOnly` propiedad para la fecha en la que se contrató a un empleado.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-129">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="5dfbe-130">La clase almacena el valor de propiedad internamente como una `Private` variable y solo el código dentro de la clase puede cambiar ese valor.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-130">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="5dfbe-131">Sin embargo, la propiedad es `Public` , y cualquier código que pueda tener acceso a la clase puede leer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5dfbe-131">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="5dfbe-132">El modificador `ReadOnly` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5dfbe-132">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="5dfbe-133">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="5dfbe-133">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="5dfbe-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5dfbe-134">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="5dfbe-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dfbe-135">See also</span></span>

- [<span data-ttu-id="5dfbe-136">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="5dfbe-136">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="5dfbe-137">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5dfbe-137">Keywords</span></span>](../keywords/index.md)

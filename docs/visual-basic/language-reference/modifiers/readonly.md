---
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
ms.openlocfilehash: 8c7e7e7c1571fd7c595ebfd54fb5767078ef41f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351282"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="b2a57-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2a57-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="b2a57-103">Especifica que una variable o una propiedad se puede leer pero no escribir.</span><span class="sxs-lookup"><span data-stu-id="b2a57-103">Specifies that a variable or property can be read but not written.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2a57-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2a57-104">Remarks</span></span>

## <a name="rules"></a><span data-ttu-id="b2a57-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="b2a57-105">Rules</span></span>

- <span data-ttu-id="b2a57-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="b2a57-106">**Declaration Context.**</span></span> <span data-ttu-id="b2a57-107">Solo se puede usar `ReadOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="b2a57-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="b2a57-108">Esto significa que el contexto de la declaración de un elemento `ReadOnly` debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b2a57-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="b2a57-109">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="b2a57-109">**Combined Modifiers.**</span></span> <span data-ttu-id="b2a57-110">No se puede especificar `ReadOnly` junto con `Static` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="b2a57-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>

- <span data-ttu-id="b2a57-111">**Asignación de un valor.**</span><span class="sxs-lookup"><span data-stu-id="b2a57-111">**Assigning a Value.**</span></span> <span data-ttu-id="b2a57-112">El código que consume una propiedad `ReadOnly` no puede establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="b2a57-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="b2a57-113">Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b2a57-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>

     <span data-ttu-id="b2a57-114">Solo puede asignar un valor a una variable `ReadOnly` en su declaración o en el constructor de una clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="b2a57-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>

## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="b2a57-115">Cuándo usar una variable de solo lectura</span><span class="sxs-lookup"><span data-stu-id="b2a57-115">When to Use a ReadOnly Variable</span></span>

<span data-ttu-id="b2a57-116">Hay situaciones en las que no se puede usar una [instrucción const](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante.</span><span class="sxs-lookup"><span data-stu-id="b2a57-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="b2a57-117">Por ejemplo, es posible que la instrucción `Const` no acepte el tipo de datos que desea asignar o que no pueda calcular el valor en tiempo de compilación con una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="b2a57-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="b2a57-118">Es posible que ni siquiera conozca el valor en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b2a57-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="b2a57-119">En estos casos, puede usar una variable `ReadOnly` para contener un valor constante.</span><span class="sxs-lookup"><span data-stu-id="b2a57-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2a57-120">Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, sus miembros se pueden cambiar incluso si la propia variable es `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="b2a57-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="b2a57-121">En el ejemplo siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="b2a57-121">The following example illustrates this.</span></span>

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

<span data-ttu-id="b2a57-122">Cuando se inicializa, la matriz a la que apunta `characterArray()` contiene "x", "y" y "z".</span><span class="sxs-lookup"><span data-stu-id="b2a57-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="b2a57-123">Dado que la variable `characterArray` es `ReadOnly`, no se puede cambiar su valor una vez inicializado. es decir, no se puede asignar una nueva matriz a ella.</span><span class="sxs-lookup"><span data-stu-id="b2a57-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="b2a57-124">Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b2a57-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="b2a57-125">Después de una llamada al procedimiento `ChangeArrayElement`, la matriz a la que apunta `characterArray()` contiene "x", "M" y "z".</span><span class="sxs-lookup"><span data-stu-id="b2a57-125">Following a call to the procedure `ChangeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>

<span data-ttu-id="b2a57-126">Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](byval.md), lo que evita que el procedimiento cambie el argumento de llamada en sí, pero permite cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b2a57-126">Note that this is similar to declaring a procedure parameter to be [ByVal](byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>

## <a name="example"></a><span data-ttu-id="b2a57-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2a57-127">Example</span></span>

<span data-ttu-id="b2a57-128">En el ejemplo siguiente se define una propiedad `ReadOnly` para la fecha en la que se contrató a un empleado.</span><span class="sxs-lookup"><span data-stu-id="b2a57-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="b2a57-129">La clase almacena el valor de propiedad internamente como una variable `Private` y solo el código dentro de la clase puede cambiar ese valor.</span><span class="sxs-lookup"><span data-stu-id="b2a57-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="b2a57-130">Sin embargo, la propiedad es `Public`y cualquier código que pueda tener acceso a la clase puede leer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b2a57-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

<span data-ttu-id="b2a57-131">El modificador `ReadOnly` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2a57-131">The `ReadOnly` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="b2a57-132">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2a57-132">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="b2a57-133">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b2a57-133">Property Statement</span></span>](../statements/property-statement.md)

## <a name="see-also"></a><span data-ttu-id="b2a57-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2a57-134">See also</span></span>

- [<span data-ttu-id="b2a57-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="b2a57-135">WriteOnly</span></span>](writeonly.md)
- [<span data-ttu-id="b2a57-136">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b2a57-136">Keywords</span></span>](../keywords/index.md)

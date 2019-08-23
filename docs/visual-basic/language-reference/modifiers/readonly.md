---
title: ReadOnly (Visual Basic)
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
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965418"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="adfc9-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adfc9-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="adfc9-103">Especifica que una variable o una propiedad se puede leer pero no escribir.</span><span class="sxs-lookup"><span data-stu-id="adfc9-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adfc9-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adfc9-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="adfc9-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="adfc9-105">Rules</span></span>  
  
- <span data-ttu-id="adfc9-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="adfc9-106">**Declaration Context.**</span></span> <span data-ttu-id="adfc9-107">Solo se puede usar `ReadOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="adfc9-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="adfc9-108">Esto significa que el contexto de la `ReadOnly` declaración de un elemento debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="adfc9-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="adfc9-109">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="adfc9-109">**Combined Modifiers.**</span></span> <span data-ttu-id="adfc9-110">No se puede `ReadOnly` especificar junto `Static` con en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="adfc9-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="adfc9-111">**Asignación de un valor.**</span><span class="sxs-lookup"><span data-stu-id="adfc9-111">**Assigning a Value.**</span></span> <span data-ttu-id="adfc9-112">El código que consume una `ReadOnly` propiedad no puede establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="adfc9-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="adfc9-113">Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="adfc9-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="adfc9-114">Puede asignar un valor a una `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="adfc9-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="adfc9-115">Cuándo usar una variable de solo lectura</span><span class="sxs-lookup"><span data-stu-id="adfc9-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="adfc9-116">Hay situaciones en las que no se puede usar una [instrucción const](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante.</span><span class="sxs-lookup"><span data-stu-id="adfc9-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="adfc9-117">Por ejemplo, es `Const` posible que la instrucción no acepte el tipo de datos que desea asignar o que no pueda calcular el valor en tiempo de compilación con una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="adfc9-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="adfc9-118">Es posible que ni siquiera conozca el valor en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="adfc9-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="adfc9-119">En estos casos, puede usar una `ReadOnly` variable para contener un valor constante.</span><span class="sxs-lookup"><span data-stu-id="adfc9-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adfc9-120">Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros aunque la propia variable `ReadOnly`sea.</span><span class="sxs-lookup"><span data-stu-id="adfc9-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="adfc9-121">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="adfc9-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="adfc9-122">Cuando se inicializa, la matriz a la que `characterArray()` señala contiene "x", "y" y "z".</span><span class="sxs-lookup"><span data-stu-id="adfc9-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="adfc9-123">Dado que la `characterArray` variable `ReadOnly`es, no se puede cambiar su valor una vez inicializado; es decir, no se puede asignar una nueva matriz a ella.</span><span class="sxs-lookup"><span data-stu-id="adfc9-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="adfc9-124">Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz.</span><span class="sxs-lookup"><span data-stu-id="adfc9-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="adfc9-125">Después de una llamada al procedimiento `changeArrayElement`, la matriz `characterArray()` a la que señala contiene "x", "M" y "z".</span><span class="sxs-lookup"><span data-stu-id="adfc9-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="adfc9-126">Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), lo que evita que el procedimiento cambie el argumento de llamada en sí, pero permite cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="adfc9-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfc9-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adfc9-127">Example</span></span>  
 <span data-ttu-id="adfc9-128">En el ejemplo siguiente se `ReadOnly` define una propiedad para la fecha en la que se contrató a un empleado.</span><span class="sxs-lookup"><span data-stu-id="adfc9-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="adfc9-129">La clase almacena el valor de propiedad internamente como `Private` una variable y solo el código dentro de la clase puede cambiar ese valor.</span><span class="sxs-lookup"><span data-stu-id="adfc9-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="adfc9-130">Sin embargo, la propiedad `Public`es, y cualquier código que pueda tener acceso a la clase puede leer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="adfc9-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="adfc9-131">El modificador `ReadOnly` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="adfc9-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="adfc9-132">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="adfc9-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="adfc9-133">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="adfc9-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="adfc9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="adfc9-134">See also</span></span>

- [<span data-ttu-id="adfc9-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="adfc9-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="adfc9-136">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="adfc9-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)

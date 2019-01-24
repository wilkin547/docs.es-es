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
ms.openlocfilehash: 741374cc375e33868239161af23a38af7680b290
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684072"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="4fc37-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc37-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="4fc37-103">Especifica que una variable o propiedad se puede leer pero no se escribe.</span><span class="sxs-lookup"><span data-stu-id="4fc37-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc37-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fc37-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4fc37-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="4fc37-105">Rules</span></span>  
  
-   <span data-ttu-id="4fc37-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="4fc37-106">**Declaration Context.**</span></span> <span data-ttu-id="4fc37-107">Solo se puede usar `ReadOnly` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="4fc37-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="4fc37-108">Esto significa que el contexto de declaración de un `ReadOnly` elemento debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4fc37-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="4fc37-109">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="4fc37-109">**Combined Modifiers.**</span></span> <span data-ttu-id="4fc37-110">No puede especificar `ReadOnly` junto con `Static` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="4fc37-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="4fc37-111">**Asignar un valor.**</span><span class="sxs-lookup"><span data-stu-id="4fc37-111">**Assigning a Value.**</span></span> <span data-ttu-id="4fc37-112">Código consume un `ReadOnly` propiedad no puede establecer su valor.</span><span class="sxs-lookup"><span data-stu-id="4fc37-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="4fc37-113">Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="4fc37-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="4fc37-114">Puede asignar un valor a un `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en el que está definida.</span><span class="sxs-lookup"><span data-stu-id="4fc37-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="4fc37-115">Cuándo usar una Variable ReadOnly</span><span class="sxs-lookup"><span data-stu-id="4fc37-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="4fc37-116">Hay situaciones en las que no se puede usar un [instrucción Const](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante.</span><span class="sxs-lookup"><span data-stu-id="4fc37-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="4fc37-117">Por ejemplo, el `Const` instrucción no puede aceptar el tipo de datos que desea asignar, o es posible que no pueda calcular el valor en tiempo de compilación con una expresión constante.</span><span class="sxs-lookup"><span data-stu-id="4fc37-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="4fc37-118">Es posible que ni siquiera sepa el valor en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4fc37-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="4fc37-119">En estos casos, puede usar un `ReadOnly` variable que contenga un valor constante.</span><span class="sxs-lookup"><span data-stu-id="4fc37-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4fc37-120">Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros incluso si es la propia variable `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="4fc37-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="4fc37-121">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4fc37-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="4fc37-122">Cuando se inicializa, la matriz señalada por `characterArray()` alberga "x", "y" y "z".</span><span class="sxs-lookup"><span data-stu-id="4fc37-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="4fc37-123">Dado que la variable `characterArray` es `ReadOnly`, no se puede cambiar su valor una vez que se ha inicializado; que es, no se puede asignar una nueva matriz a él.</span><span class="sxs-lookup"><span data-stu-id="4fc37-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="4fc37-124">Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4fc37-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="4fc37-125">Después de una llamada al procedimiento `changeArrayElement`, la matriz señalada por `characterArray()` alberga "x", "M" y "z".</span><span class="sxs-lookup"><span data-stu-id="4fc37-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="4fc37-126">Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), lo que impide que el procedimiento cambia el argumento de llamada, pero le permite cambiar sus miembros.</span><span class="sxs-lookup"><span data-stu-id="4fc37-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fc37-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fc37-127">Example</span></span>  
 <span data-ttu-id="4fc37-128">En el ejemplo siguiente se define un `ReadOnly` propiedad para la fecha en que se contrató a un empleado.</span><span class="sxs-lookup"><span data-stu-id="4fc37-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="4fc37-129">La clase almacena internamente de la propiedad como valor un `Private` variable y solo el código dentro de la clase puede cambiar ese valor.</span><span class="sxs-lookup"><span data-stu-id="4fc37-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="4fc37-130">Sin embargo, la propiedad es `Public`, y cualquier código que puede tener acceso a la clase puede leer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4fc37-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="4fc37-131">El modificador `ReadOnly` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fc37-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4fc37-132">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4fc37-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="4fc37-133">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4fc37-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4fc37-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fc37-134">See also</span></span>
- [<span data-ttu-id="4fc37-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="4fc37-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="4fc37-136">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4fc37-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)

---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 12c81a9a0651088a348afeaff3b71935d289da53
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816288"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="d158e-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d158e-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="d158e-103">Especifica que uno o varios elementos de programación declarados están asociados con una clase o estructura en general y no con una instancia específica de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d158e-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d158e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d158e-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="d158e-105">Cuándo usar compartido</span><span class="sxs-lookup"><span data-stu-id="d158e-105">When to Use Shared</span></span>  
 <span data-ttu-id="d158e-106">Compartir un miembro de una clase o estructura pone a disposición de todas las instancias, en lugar de *no compartido*, donde cada instancia mantiene su propia copia.</span><span class="sxs-lookup"><span data-stu-id="d158e-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="d158e-107">Esto es útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d158e-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="d158e-108">Si esa variable se declara `Shared`y, a continuación, todas las instancias a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias de tener acceso al valor actualizado.</span><span class="sxs-lookup"><span data-stu-id="d158e-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="d158e-109">Uso compartido no modifica el nivel de acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="d158e-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="d158e-110">Por ejemplo, se puede compartir un miembro de clase y privado (accesible únicamente desde dentro de la clase), o no compartido y público.</span><span class="sxs-lookup"><span data-stu-id="d158e-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="d158e-111">Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d158e-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d158e-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="d158e-112">Rules</span></span>  
  
-   <span data-ttu-id="d158e-113">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="d158e-113">**Declaration Context.**</span></span> <span data-ttu-id="d158e-114">Solo se puede usar `Shared` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="d158e-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="d158e-115">Esto significa que el contexto de declaración de un `Shared` elemento debe ser una clase o estructura y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d158e-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="d158e-116">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="d158e-116">**Combined Modifiers.**</span></span> <span data-ttu-id="d158e-117">No puede especificar `Shared` junto con [invalida](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), o [ Estático](../../../visual-basic/language-reference/modifiers/static.md) en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="d158e-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="d158e-118">**Acceso a.**</span><span class="sxs-lookup"><span data-stu-id="d158e-118">**Accessing.**</span></span> <span data-ttu-id="d158e-119">Tener acceso a un elemento compartido calificando con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d158e-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="d158e-120">Incluso no es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.</span><span class="sxs-lookup"><span data-stu-id="d158e-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="d158e-121">En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuestos por el <xref:System.Double> estructura.</span><span class="sxs-lookup"><span data-stu-id="d158e-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="d158e-122">**Uso compartido implícito.**</span><span class="sxs-lookup"><span data-stu-id="d158e-122">**Implicit Sharing.**</span></span> <span data-ttu-id="d158e-123">No puede usar el `Shared` modificador en un [instrucción Const](../../../visual-basic/language-reference/statements/const-statement.md), pero las constantes se comparten de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="d158e-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="d158e-124">De forma similar, no se puede declarar un miembro de un módulo o una interfaz como `Shared`, pero se compartían de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="d158e-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d158e-125">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d158e-125">Behavior</span></span>  
  
-   <span data-ttu-id="d158e-126">**Almacenamiento.**</span><span class="sxs-lookup"><span data-stu-id="d158e-126">**Storage.**</span></span> <span data-ttu-id="d158e-127">Una variable compartida o un evento se almacena en memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d158e-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="d158e-128">De forma similar, un procedimiento compartido o una propiedad contiene sólo un conjunto de variables locales.</span><span class="sxs-lookup"><span data-stu-id="d158e-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="d158e-129">**Acceso mediante una Variable de instancia.**</span><span class="sxs-lookup"><span data-stu-id="d158e-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="d158e-130">Es posible tener acceso a un elemento compartido calificando el nombre de una variable que contiene una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d158e-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="d158e-131">Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso a través del nombre de clase o estructura en lugar de la variable.</span><span class="sxs-lookup"><span data-stu-id="d158e-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="d158e-132">**Acceso mediante una expresión de instancia.**</span><span class="sxs-lookup"><span data-stu-id="d158e-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="d158e-133">Si tiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador hace que el acceso a través del nombre de clase o estructura en lugar de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="d158e-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="d158e-134">Esto produce resultados inesperados si va a usar la expresión para realizar otras acciones, así como devolver la instancia.</span><span class="sxs-lookup"><span data-stu-id="d158e-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="d158e-135">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d158e-135">The following example illustrates this.</span></span>  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="d158e-136">En el ejemplo anterior, el compilador genera un mensaje de advertencia dos veces el código tiene acceso a la variable compartida `total` a través de una instancia.</span><span class="sxs-lookup"><span data-stu-id="d158e-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="d158e-137">En cada caso, obtiene acceso directamente a través de la clase `shareTotal` y no hacer uso de cualquier instancia.</span><span class="sxs-lookup"><span data-stu-id="d158e-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="d158e-138">En el caso de la llamada al procedimiento prevista `returnClass`, esto significa que incluso no generar una llamada a `returnClass`, por lo que no se realiza la acción adicional de mostrar "Function returnClass() called".</span><span class="sxs-lookup"><span data-stu-id="d158e-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="d158e-139">El modificador `Shared` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d158e-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d158e-140">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="d158e-141">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="d158e-142">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d158e-143">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="d158e-144">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d158e-145">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d158e-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d158e-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d158e-146">See also</span></span>

- [<span data-ttu-id="d158e-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="d158e-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="d158e-148">Static</span><span class="sxs-lookup"><span data-stu-id="d158e-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="d158e-149">Duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d158e-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="d158e-150">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d158e-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d158e-151">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d158e-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d158e-152">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="d158e-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

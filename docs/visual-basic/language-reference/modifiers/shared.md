---
title: Compartido
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
ms.openlocfilehash: 000cc13bc6e80914e9a21b6ee60e91127809ee08
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307090"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="2e963-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e963-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="2e963-103">Especifica que uno o varios elementos de programación declarados están asociados a una clase o estructura de gran tamaño, y no a una instancia específica de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2e963-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="2e963-104">Cuándo usar Shared</span><span class="sxs-lookup"><span data-stu-id="2e963-104">When to Use Shared</span></span>

<span data-ttu-id="2e963-105">Compartir un miembro de una clase o estructura lo pone a disposición de todas las instancias, en lugar de *no compartidas*, donde cada instancia conserva su propia copia.</span><span class="sxs-lookup"><span data-stu-id="2e963-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="2e963-106">Esto resulta útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e963-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="2e963-107">Si declara que esa variable es `Shared` , todas las instancias acceden a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias acceden al valor actualizado.</span><span class="sxs-lookup"><span data-stu-id="2e963-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="2e963-108">El uso compartido no modifica el nivel de acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="2e963-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="2e963-109">Por ejemplo, un miembro de clase puede ser compartido y privado (accesible solo desde dentro de la clase), o no compartido y público.</span><span class="sxs-lookup"><span data-stu-id="2e963-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="2e963-110">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e963-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="2e963-111">Reglas</span><span class="sxs-lookup"><span data-stu-id="2e963-111">Rules</span></span>

- <span data-ttu-id="2e963-112">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="2e963-112">**Declaration Context.**</span></span> <span data-ttu-id="2e963-113">Solo se puede usar `Shared` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="2e963-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="2e963-114">Esto significa que el contexto de la declaración de un `Shared` elemento debe ser una clase o estructura, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2e963-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="2e963-115">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="2e963-115">**Combined Modifiers.**</span></span> <span data-ttu-id="2e963-116">No se puede especificar `Shared` junto con [invalidaciones](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)o [static](../../../visual-basic/language-reference/modifiers/static.md) en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="2e963-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="2e963-117">**Acceso a.**</span><span class="sxs-lookup"><span data-stu-id="2e963-117">**Accessing.**</span></span> <span data-ttu-id="2e963-118">Puede tener acceso a un elemento compartido si lo califica con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2e963-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="2e963-119">No es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.</span><span class="sxs-lookup"><span data-stu-id="2e963-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="2e963-120">En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuesto por la <xref:System.Double> estructura.</span><span class="sxs-lookup"><span data-stu-id="2e963-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="2e963-121">**Uso compartido implícito.**</span><span class="sxs-lookup"><span data-stu-id="2e963-121">**Implicit Sharing.**</span></span> <span data-ttu-id="2e963-122">No se puede usar el `Shared` modificador en una [instrucción const](../../../visual-basic/language-reference/statements/const-statement.md), pero las constantes se comparten implícitamente.</span><span class="sxs-lookup"><span data-stu-id="2e963-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="2e963-123">Del mismo modo, no puede declarar un miembro de un módulo o una interfaz para que sea `Shared` , pero se comparten implícitamente.</span><span class="sxs-lookup"><span data-stu-id="2e963-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="2e963-124">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="2e963-124">Behavior</span></span>

- <span data-ttu-id="2e963-125">**Discos.**</span><span class="sxs-lookup"><span data-stu-id="2e963-125">**Storage.**</span></span> <span data-ttu-id="2e963-126">Una variable o evento compartido se almacena en la memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2e963-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="2e963-127">De forma similar, un procedimiento compartido o una propiedad solo contiene un conjunto de variables locales.</span><span class="sxs-lookup"><span data-stu-id="2e963-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="2e963-128">**Obtener acceso a través de una variable de instancia.**</span><span class="sxs-lookup"><span data-stu-id="2e963-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="2e963-129">Es posible obtener acceso a un elemento compartido si se califica con el nombre de una variable que contiene una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2e963-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="2e963-130">Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso se realice a través del nombre de la clase o la estructura en lugar de la variable.</span><span class="sxs-lookup"><span data-stu-id="2e963-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="2e963-131">**Obtener acceso a través de una expresión de instancia.**</span><span class="sxs-lookup"><span data-stu-id="2e963-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="2e963-132">Si obtiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador realiza el acceso a través del nombre de la clase o la estructura en lugar de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="2e963-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="2e963-133">Esto produce resultados inesperados si desea que la expresión realice otras acciones, así como para devolver la instancia.</span><span class="sxs-lookup"><span data-stu-id="2e963-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="2e963-134">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2e963-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="2e963-135">En el ejemplo anterior, el compilador genera un mensaje de advertencia ambas veces el código tiene acceso a la propiedad compartida `Total` a través de una instancia de.</span><span class="sxs-lookup"><span data-stu-id="2e963-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="2e963-136">En cada caso, hace que el acceso se realice directamente a través de la clase `ShareTotal` y no usa ninguna instancia de.</span><span class="sxs-lookup"><span data-stu-id="2e963-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="2e963-137">En el caso de la llamada prevista al procedimiento `ReturnClass` , esto significa que no genera ni siquiera una llamada a `ReturnClass` , por lo que no se realiza la acción adicional de mostrar "función ReturnClass () llamada".</span><span class="sxs-lookup"><span data-stu-id="2e963-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="2e963-138">El modificador `Shared` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e963-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="2e963-139">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="2e963-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="2e963-140">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e963-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="2e963-141">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="2e963-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="2e963-142">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="2e963-142">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="2e963-143">Property Statement</span><span class="sxs-lookup"><span data-stu-id="2e963-143">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="2e963-144">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="2e963-144">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="2e963-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e963-145">See also</span></span>

- [<span data-ttu-id="2e963-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="2e963-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="2e963-147">Estática</span><span class="sxs-lookup"><span data-stu-id="2e963-147">Static</span></span>](static.md)
- [<span data-ttu-id="2e963-148">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e963-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="2e963-149">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2e963-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="2e963-150">Estructuras</span><span class="sxs-lookup"><span data-stu-id="2e963-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="2e963-151">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="2e963-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)

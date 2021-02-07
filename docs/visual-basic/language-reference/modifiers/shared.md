---
description: 'Más información acerca de: Shared (Visual Basic)'
title: Shared
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
ms.openlocfilehash: 0cc671c67486d01026f2283837448db7b00c1a0a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700759"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="59066-103">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59066-103">Shared (Visual Basic)</span></span>

<span data-ttu-id="59066-104">Especifica que uno o varios elementos de programación declarados están asociados a una clase o estructura de gran tamaño, y no a una instancia específica de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="59066-104">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="59066-105">Cuándo usar Shared</span><span class="sxs-lookup"><span data-stu-id="59066-105">When to Use Shared</span></span>

<span data-ttu-id="59066-106">Compartir un miembro de una clase o estructura lo pone a disposición de todas las instancias, en lugar de *no compartidas*, donde cada instancia conserva su propia copia.</span><span class="sxs-lookup"><span data-stu-id="59066-106">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="59066-107">El uso compartido es útil, por ejemplo, si el valor de una variable se aplica a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59066-107">Sharing is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="59066-108">Si declara que esa variable es `Shared` , todas las instancias acceden a la misma ubicación de almacenamiento y, si una instancia cambia el valor de la variable, todas las instancias acceden al valor actualizado.</span><span class="sxs-lookup"><span data-stu-id="59066-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="59066-109">El uso compartido no modifica el nivel de acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="59066-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="59066-110">Por ejemplo, un miembro de clase puede ser compartido y privado (accesible solo desde dentro de la clase), o no compartido y público.</span><span class="sxs-lookup"><span data-stu-id="59066-110">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="59066-111">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="59066-111">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="59066-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="59066-112">Rules</span></span>

- <span data-ttu-id="59066-113">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="59066-113">**Declaration Context.**</span></span> <span data-ttu-id="59066-114">Solo se puede usar `Shared` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="59066-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="59066-115">Esto significa que el contexto de la declaración de un `Shared` elemento debe ser una clase o estructura, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="59066-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="59066-116">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="59066-116">**Combined Modifiers.**</span></span> <span data-ttu-id="59066-117">No se puede especificar `Shared` junto con [invalidaciones](overrides.md), [Overridable](overridable.md), [NotOverridable](notoverridable.md), [MustOverride](mustoverride.md)o [static](static.md) en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="59066-117">You cannot specify `Shared` together with [Overrides](overrides.md), [Overridable](overridable.md), [NotOverridable](notoverridable.md), [MustOverride](mustoverride.md), or [Static](static.md) in the same declaration.</span></span>

- <span data-ttu-id="59066-118">**Acceso a.**</span><span class="sxs-lookup"><span data-stu-id="59066-118">**Accessing.**</span></span> <span data-ttu-id="59066-119">Puede tener acceso a un elemento compartido si lo califica con su nombre de clase o estructura, no con el nombre de variable de una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="59066-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="59066-120">No es necesario crear una instancia de una clase o estructura para tener acceso a sus miembros compartidos.</span><span class="sxs-lookup"><span data-stu-id="59066-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="59066-121">En el ejemplo siguiente se llama al procedimiento compartido <xref:System.Double.IsNaN%2A> expuesto por la <xref:System.Double> estructura.</span><span class="sxs-lookup"><span data-stu-id="59066-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="59066-122">**Uso compartido implícito.**</span><span class="sxs-lookup"><span data-stu-id="59066-122">**Implicit Sharing.**</span></span> <span data-ttu-id="59066-123">No se puede usar el `Shared` modificador en una [instrucción const](../statements/const-statement.md), pero las constantes se comparten implícitamente.</span><span class="sxs-lookup"><span data-stu-id="59066-123">You cannot use the `Shared` modifier in a [Const Statement](../statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="59066-124">Del mismo modo, no puede declarar un miembro de un módulo o una interfaz para que sea `Shared` , pero se comparten implícitamente.</span><span class="sxs-lookup"><span data-stu-id="59066-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="59066-125">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="59066-125">Behavior</span></span>

- <span data-ttu-id="59066-126">**Almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="59066-126">**Storage.**</span></span> <span data-ttu-id="59066-127">Una variable o evento compartido se almacena en la memoria solo una vez, independientemente del número de instancias que cree de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="59066-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="59066-128">De forma similar, un procedimiento compartido o una propiedad solo contiene un conjunto de variables locales.</span><span class="sxs-lookup"><span data-stu-id="59066-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="59066-129">**Obtener acceso a través de una variable de instancia.**</span><span class="sxs-lookup"><span data-stu-id="59066-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="59066-130">Es posible obtener acceso a un elemento compartido si se califica con el nombre de una variable que contiene una instancia específica de su clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="59066-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="59066-131">Aunque esto suele funcionar según lo esperado, el compilador genera un mensaje de advertencia y hace que el acceso se realice a través del nombre de la clase o la estructura en lugar de la variable.</span><span class="sxs-lookup"><span data-stu-id="59066-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="59066-132">**Obtener acceso a través de una expresión de instancia.**</span><span class="sxs-lookup"><span data-stu-id="59066-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="59066-133">Si obtiene acceso a un elemento compartido a través de una expresión que devuelve una instancia de su clase o estructura, el compilador realiza el acceso a través del nombre de la clase o la estructura en lugar de evaluar la expresión.</span><span class="sxs-lookup"><span data-stu-id="59066-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="59066-134">Este acceso produce resultados inesperados si desea que la expresión realice otras acciones, así como para devolver la instancia.</span><span class="sxs-lookup"><span data-stu-id="59066-134">This access produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="59066-135">En el ejemplo siguiente se muestra esta situación.</span><span class="sxs-lookup"><span data-stu-id="59066-135">The following example illustrates this situation.</span></span>
  
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

     <span data-ttu-id="59066-136">En el ejemplo anterior, el compilador genera un mensaje de advertencia ambas veces el código tiene acceso a la propiedad compartida `Total` a través de una instancia de.</span><span class="sxs-lookup"><span data-stu-id="59066-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="59066-137">En cada caso, realiza el acceso directamente a través de la clase `ShareTotal` y no hace uso de ninguna instancia.</span><span class="sxs-lookup"><span data-stu-id="59066-137">In each case, it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="59066-138">En el caso de la llamada prevista al procedimiento `ReturnClass` , esto significa que no genera ni siquiera una llamada a `ReturnClass` , por lo que no se realiza la acción adicional de mostrar "función ReturnClass () llamada".</span><span class="sxs-lookup"><span data-stu-id="59066-138">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="59066-139">El modificador `Shared` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="59066-139">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="59066-140">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="59066-140">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="59066-141">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="59066-141">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="59066-142">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="59066-142">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="59066-143">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="59066-143">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="59066-144">Property Statement</span><span class="sxs-lookup"><span data-stu-id="59066-144">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="59066-145">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="59066-145">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="59066-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="59066-146">See also</span></span>

- [<span data-ttu-id="59066-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="59066-147">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="59066-148">Estática</span><span class="sxs-lookup"><span data-stu-id="59066-148">Static</span></span>](static.md)
- [<span data-ttu-id="59066-149">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59066-149">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="59066-150">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="59066-150">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="59066-151">Estructuras</span><span class="sxs-lookup"><span data-stu-id="59066-151">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="59066-152">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="59066-152">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)

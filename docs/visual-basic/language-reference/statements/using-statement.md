---
title: Using (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957546"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="bf702-102">Using (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf702-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="bf702-103">Declara el principio de un `Using` bloque y, opcionalmente, adquiere los recursos del sistema que controla el bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf702-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf702-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="bf702-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="bf702-105">Parts</span></span>  
  
|<span data-ttu-id="bf702-106">Término</span><span class="sxs-lookup"><span data-stu-id="bf702-106">Term</span></span>|<span data-ttu-id="bf702-107">Definición</span><span class="sxs-lookup"><span data-stu-id="bf702-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="bf702-108">Necesario si no se proporciona `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="bf702-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="bf702-109">Lista de uno o varios recursos del sistema que `Using` controla este bloque, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="bf702-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="bf702-110">Necesario si no se proporciona `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="bf702-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="bf702-111">Variable o expresión de referencia que hace referencia a un recurso del sistema que `Using` va a controlar este bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="bf702-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bf702-112">Optional.</span></span> <span data-ttu-id="bf702-113">Bloque de instrucciones que ejecuta `Using` el bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="bf702-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bf702-114">Required.</span></span> <span data-ttu-id="bf702-115">Finaliza la definición del `Using` bloque y desecha todos los recursos que controle.</span><span class="sxs-lookup"><span data-stu-id="bf702-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="bf702-116">Cada recurso `resourcelist` del elemento tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf702-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="bf702-117">-o bien-</span><span class="sxs-lookup"><span data-stu-id="bf702-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="bf702-118">Elementos resourcelist</span><span class="sxs-lookup"><span data-stu-id="bf702-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="bf702-119">Término</span><span class="sxs-lookup"><span data-stu-id="bf702-119">Term</span></span>|<span data-ttu-id="bf702-120">Definición</span><span class="sxs-lookup"><span data-stu-id="bf702-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="bf702-121">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bf702-121">Required.</span></span> <span data-ttu-id="bf702-122">Variable de referencia que hace referencia a un recurso del `Using` sistema que controla el bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="bf702-123">Obligatorio si la `Using` instrucción adquiere el recurso.</span><span class="sxs-lookup"><span data-stu-id="bf702-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="bf702-124">Si ya ha adquirido el recurso, utilice la segunda alternativa de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="bf702-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="bf702-125">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bf702-125">Required.</span></span> <span data-ttu-id="bf702-126">La clase del recurso.</span><span class="sxs-lookup"><span data-stu-id="bf702-126">The class of the resource.</span></span> <span data-ttu-id="bf702-127">La clase debe implementar la <xref:System.IDisposable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="bf702-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="bf702-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bf702-128">Optional.</span></span> <span data-ttu-id="bf702-129">Lista de argumentos que se pasan al constructor para crear una instancia de `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="bf702-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="bf702-130">Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="bf702-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="bf702-131">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bf702-131">Required.</span></span> <span data-ttu-id="bf702-132">Variable o expresión que hace referencia a un recurso del sistema que `resourcetype`cumple los requisitos de.</span><span class="sxs-lookup"><span data-stu-id="bf702-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="bf702-133">Si usa la segunda alternativa de sintaxis, debe adquirir el recurso antes de pasar el control a `Using` la instrucción.</span><span class="sxs-lookup"><span data-stu-id="bf702-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf702-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf702-134">Remarks</span></span>  
 <span data-ttu-id="bf702-135">A veces, el código requiere un recurso no administrado, como un identificador de archivo, un contenedor COM o una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="bf702-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="bf702-136">Un `Using` bloque garantiza la eliminación de uno o varios de estos recursos cuando el código finaliza con ellos.</span><span class="sxs-lookup"><span data-stu-id="bf702-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="bf702-137">Esto hace que estén disponibles para que los use otro código.</span><span class="sxs-lookup"><span data-stu-id="bf702-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="bf702-138">Los recursos administrados son eliminados por el recolector de elementos no utilizados (GC) de .NET Framework sin necesidad de codificación adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="bf702-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="bf702-139">No necesita un `Using` bloque para los recursos administrados.</span><span class="sxs-lookup"><span data-stu-id="bf702-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="bf702-140">Sin embargo, todavía puede usar un `Using` bloque para forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bf702-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="bf702-141">Un `Using` bloque tiene tres partes: adquisición, uso y eliminación.</span><span class="sxs-lookup"><span data-stu-id="bf702-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="bf702-142">La *adquisición* significa crear una variable e inicializarla para hacer referencia al recurso del sistema.</span><span class="sxs-lookup"><span data-stu-id="bf702-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="bf702-143">La `Using` instrucción puede adquirir uno o más recursos, o bien puede adquirir exactamente un recurso antes de entrar en el bloque y suministrarlo `Using` a la instrucción.</span><span class="sxs-lookup"><span data-stu-id="bf702-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="bf702-144">Si proporciona `resourceexpression`, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bf702-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="bf702-145">El *uso* significa tener acceso a los recursos y realizar acciones con ellos.</span><span class="sxs-lookup"><span data-stu-id="bf702-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="bf702-146">Las instrucciones entre `Using` y `End Using` representan el uso de los recursos.</span><span class="sxs-lookup"><span data-stu-id="bf702-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="bf702-147">La *eliminación* significa llamar <xref:System.IDisposable.Dispose%2A> al método en el objeto `resourcename`de.</span><span class="sxs-lookup"><span data-stu-id="bf702-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="bf702-148">Esto permite que el objeto finalice correctamente sus recursos.</span><span class="sxs-lookup"><span data-stu-id="bf702-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="bf702-149">La `End Using` instrucción desecha los recursos bajo el `Using` control del bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="bf702-150">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="bf702-150">Behavior</span></span>  
 <span data-ttu-id="bf702-151">Un `Using` bloque se comporta `Try`como... construcción en la que `Try` el bloque usa los recursos y `Finally` el bloque los desecha. `Finally`</span><span class="sxs-lookup"><span data-stu-id="bf702-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="bf702-152">Por este motivo, el `Using` bloque garantiza la eliminación de los recursos, independientemente de cómo salga del bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="bf702-153">Esto es así incluso en el caso de una excepción no controlada, excepto para <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="bf702-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="bf702-154">El ámbito de cada variable de recurso adquirido por `Using` la instrucción se limita `Using` al bloque.</span><span class="sxs-lookup"><span data-stu-id="bf702-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="bf702-155">Si especifica más de un recurso del sistema en la `Using` instrucción, el efecto es el mismo que si `Using` anidara bloques uno dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="bf702-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="bf702-156">Si `resourcename` <xref:System.IDisposable.Dispose%2A> es `Nothing`, no se realiza ninguna llamada a y no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="bf702-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="bf702-157">Control de excepciones estructurado dentro de un bloque Using</span><span class="sxs-lookup"><span data-stu-id="bf702-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="bf702-158">Si necesita controlar una excepción que puede producirse en el `Using` bloque, puede agregar `Try`una... `Finally` construir en él.</span><span class="sxs-lookup"><span data-stu-id="bf702-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="bf702-159">Si necesita controlar el caso en el que la `Using` instrucción no puede adquirir un recurso correctamente, puede comprobar si `resourcename` es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="bf702-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="bf702-160">Control de excepciones estructurado en lugar de un bloque Using</span><span class="sxs-lookup"><span data-stu-id="bf702-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="bf702-161">Si necesita un control más preciso sobre la adquisición de los recursos o si necesita código adicional en el `Finally` bloque, puede volver a escribir el `Using` bloque como `Try`... `Finally` construcción.</span><span class="sxs-lookup"><span data-stu-id="bf702-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="bf702-162">En el ejemplo siguiente se `Try` muestran `Using` esqueleto y construcciones que son equivalentes en la adquisición `resource`y la eliminación de.</span><span class="sxs-lookup"><span data-stu-id="bf702-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
> <span data-ttu-id="bf702-163">El código dentro del `Using` bloque no debe asignar el `resourcename` objeto a otra variable.</span><span class="sxs-lookup"><span data-stu-id="bf702-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="bf702-164">Al salir del `Using` bloque, el recurso se desecha y la otra variable no puede tener acceso al recurso al que señala.</span><span class="sxs-lookup"><span data-stu-id="bf702-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf702-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf702-165">Example</span></span>  
 <span data-ttu-id="bf702-166">En el ejemplo siguiente se crea un archivo denominado log. txt y se escriben dos líneas de texto en el archivo.</span><span class="sxs-lookup"><span data-stu-id="bf702-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="bf702-167">En el ejemplo también se lee el mismo archivo y se muestran las líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="bf702-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="bf702-168">Dado que <xref:System.IO.TextWriter> las <xref:System.IO.TextReader> clases y implementan la <xref:System.IDisposable> interfaz, el código `Using` puede usar instrucciones para asegurarse de que el archivo se cierra correctamente después de las operaciones de escritura y lectura.</span><span class="sxs-lookup"><span data-stu-id="bf702-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="bf702-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf702-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="bf702-170">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bf702-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="bf702-171">Cómo: Desechar un recurso del sistema</span><span class="sxs-lookup"><span data-stu-id="bf702-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

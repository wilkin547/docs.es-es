---
title: Using (Instrucción, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="80672-102">Using (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80672-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="80672-103">Declara el principio de un `Using` bloquear y, opcionalmente, adquiere los recursos del sistema que controla el bloque.</span><span class="sxs-lookup"><span data-stu-id="80672-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80672-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80672-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="80672-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="80672-105">Parts</span></span>  
  
|<span data-ttu-id="80672-106">Término</span><span class="sxs-lookup"><span data-stu-id="80672-106">Term</span></span>|<span data-ttu-id="80672-107">Definición</span><span class="sxs-lookup"><span data-stu-id="80672-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="80672-108">Obligatorio si no se proporciona `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="80672-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="80672-109">Lista de uno o más recursos del sistema que este `Using` Bloquear controles, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="80672-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="80672-110">Obligatorio si no se proporciona `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="80672-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="80672-111">Variable de referencia o una expresión que hace referencia a un recurso del sistema esté controlada por esto `Using` bloque.</span><span class="sxs-lookup"><span data-stu-id="80672-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="80672-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="80672-112">Optional.</span></span> <span data-ttu-id="80672-113">Bloque de instrucciones que el `Using` bloquear ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="80672-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="80672-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80672-114">Required.</span></span> <span data-ttu-id="80672-115">Termina la definición de la `Using` bloque y elimina todos los recursos que controla.</span><span class="sxs-lookup"><span data-stu-id="80672-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="80672-116">Cada recurso de la `resourcelist` parte tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="80672-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="80672-117">O bien</span><span class="sxs-lookup"><span data-stu-id="80672-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="80672-118">Partes de resourceList</span><span class="sxs-lookup"><span data-stu-id="80672-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="80672-119">Término</span><span class="sxs-lookup"><span data-stu-id="80672-119">Term</span></span>|<span data-ttu-id="80672-120">Definición</span><span class="sxs-lookup"><span data-stu-id="80672-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="80672-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80672-121">Required.</span></span> <span data-ttu-id="80672-122">Variable de referencia que hace referencia a un recurso del sistema que la `Using` impedir que los controles.</span><span class="sxs-lookup"><span data-stu-id="80672-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="80672-123">Obligatorio si la `Using` instrucción adquiere el recurso.</span><span class="sxs-lookup"><span data-stu-id="80672-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="80672-124">Si ya ha adquirido el recurso, use la segunda alternativa de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="80672-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="80672-125">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80672-125">Required.</span></span> <span data-ttu-id="80672-126">La clase del recurso.</span><span class="sxs-lookup"><span data-stu-id="80672-126">The class of the resource.</span></span> <span data-ttu-id="80672-127">La clase debe implementar la <xref:System.IDisposable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="80672-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="80672-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="80672-128">Optional.</span></span> <span data-ttu-id="80672-129">Lista de argumentos que está pasando al constructor para crear una instancia de `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="80672-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="80672-130">Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="80672-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="80672-131">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80672-131">Required.</span></span> <span data-ttu-id="80672-132">Variable o expresión que hace referencia a un recurso del sistema que satisface los requisitos de `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="80672-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="80672-133">Si utiliza la segunda alternativa de la sintaxis, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="80672-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80672-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80672-134">Remarks</span></span>  
 <span data-ttu-id="80672-135">A veces el código requiere un recurso no administrado, como un identificador de archivos, un contenedor COM o una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="80672-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="80672-136">Un `Using` bloque garantiza la eliminación de uno o varios de estos recursos cuando el código termine con ellos.</span><span class="sxs-lookup"><span data-stu-id="80672-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="80672-137">Esto hace que estén disponibles para otro código.</span><span class="sxs-lookup"><span data-stu-id="80672-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="80672-138">Recursos administrados se eliminan mediante el recolector de elementos no utilizados (GC) de .NET Framework sin necesidad de código adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="80672-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="80672-139">No es necesario un `Using` bloque para los recursos administrados.</span><span class="sxs-lookup"><span data-stu-id="80672-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="80672-140">Sin embargo, todavía puede usar un `Using` bloque para forzar la eliminación de un recurso administrado en lugar de esperar el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="80672-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="80672-141">Un `Using` bloque tiene tres partes: adquisición, uso y eliminación.</span><span class="sxs-lookup"><span data-stu-id="80672-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="80672-142">*Adquisición* significa crear una variable y su inicialización para hacer referencia a los recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="80672-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="80672-143">El `Using` instrucción puede adquirir uno o más recursos, o puede adquirir exactamente un recurso antes de entrar en el bloque y proporcionarlo a la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="80672-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="80672-144">Si proporciona `resourceexpression`, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="80672-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="80672-145">*Uso* significa obtener acceso a los recursos y realizar acciones con ellos.</span><span class="sxs-lookup"><span data-stu-id="80672-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="80672-146">Las instrucciones situadas entre `Using` y `End Using` representan el uso de los recursos.</span><span class="sxs-lookup"><span data-stu-id="80672-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="80672-147">*Eliminación de* significa llamar a la <xref:System.IDisposable.Dispose%2A> método en el objeto de `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="80672-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="80672-148">Esto permite que el objeto terminar limpiamente sus recursos.</span><span class="sxs-lookup"><span data-stu-id="80672-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="80672-149">El `End Using` instrucción se deshace de los recursos en el `Using` control del bloque.</span><span class="sxs-lookup"><span data-stu-id="80672-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="80672-150">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="80672-150">Behavior</span></span>  
 <span data-ttu-id="80672-151">A `Using` bloque se comporta como un `Try`... `Finally` construcción en el que el `Try` bloque usa los recursos y la `Finally` bloque se deshace de ellos.</span><span class="sxs-lookup"><span data-stu-id="80672-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="80672-152">Por este motivo, la `Using` bloque garantiza la eliminación de los recursos, independientemente de cómo salga del bloque.</span><span class="sxs-lookup"><span data-stu-id="80672-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="80672-153">Esto es cierto incluso si se produce una excepción no controlada, excepto para un <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="80672-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="80672-154">El ámbito de cada variable de recurso adquirido por el `Using` instrucción se limita a la `Using` bloque.</span><span class="sxs-lookup"><span data-stu-id="80672-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="80672-155">Si especifica más de un recurso del sistema en el `Using` instrucción, el efecto es el mismo que si anidados `Using` bloquea uno dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="80672-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="80672-156">Si `resourcename` es `Nothing`, sin una llamada a <xref:System.IDisposable.Dispose%2A> se realiza, y no se produce ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="80672-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="80672-157">Estructurado de excepciones dentro de un bloque Using</span><span class="sxs-lookup"><span data-stu-id="80672-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="80672-158">Si necesita controlar una excepción que puede producirse en el `Using` bloque, puede agregar una completa `Try`... `Finally` construcción a él.</span><span class="sxs-lookup"><span data-stu-id="80672-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="80672-159">Si necesita controlar el caso donde el `Using` instrucción no se realiza correctamente en adquirir un recurso, puede probar para ver si `resourcename` es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="80672-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="80672-160">Control en lugar de un bloque Using estructurado de excepciones</span><span class="sxs-lookup"><span data-stu-id="80672-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="80672-161">Si necesita un control más preciso sobre la adquisición de los recursos, o si necesita código adicional en el `Finally` bloque, puede volver a escribir el `Using` bloquear como un `Try`... `Finally` construcción.</span><span class="sxs-lookup"><span data-stu-id="80672-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="80672-162">En el ejemplo siguiente se muestra el esqueleto `Try` y `Using` construcciones que son equivalentes en la adquisición y eliminación de `resource`.</span><span class="sxs-lookup"><span data-stu-id="80672-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
>  <span data-ttu-id="80672-163">El código dentro de la `Using` bloque no debe asignar el objeto de `resourcename` a otra variable.</span><span class="sxs-lookup"><span data-stu-id="80672-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="80672-164">Al salir del `Using` bloque, el recurso se elimina, y la otra variable no puede tener acceso al recurso al que señala.</span><span class="sxs-lookup"><span data-stu-id="80672-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80672-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80672-165">Example</span></span>  
 <span data-ttu-id="80672-166">En el ejemplo siguiente se crea un archivo que se denomina log.txt y escribe dos líneas de texto en el archivo.</span><span class="sxs-lookup"><span data-stu-id="80672-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="80672-167">El ejemplo también lee ese mismo archivo y muestra las líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="80672-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="80672-168">Dado que el <xref:System.IO.TextWriter> y <xref:System.IO.TextReader> clases implementan la <xref:System.IDisposable> interfaz, el código puede usar `Using` instrucciones para asegurarse de que el archivo se cierra después de la escritura y las operaciones de lectura correctamente.</span><span class="sxs-lookup"><span data-stu-id="80672-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="80672-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="80672-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="80672-170">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="80672-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="80672-171">Deshacerse de un recurso del sistema</span><span class="sxs-lookup"><span data-stu-id="80672-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

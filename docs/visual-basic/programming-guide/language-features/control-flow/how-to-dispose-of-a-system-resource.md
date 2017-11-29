---
title: "Cómo: Deshacerse de un recurso del sistema (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b5c65c9d123c6f481852eb249cb4d479a180c5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="b827e-102">Cómo: Deshacerse de un recurso del sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b827e-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="b827e-103">Puede usar un `Using` bloque para garantizar que el sistema dispone de un recurso cuando el código sale del bloque.</span><span class="sxs-lookup"><span data-stu-id="b827e-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="b827e-104">Esto es útil si está usando un recurso del sistema que consume una gran cantidad de memoria o que otros componentes también va a usar.</span><span class="sxs-lookup"><span data-stu-id="b827e-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="b827e-105">Para eliminar una conexión de base de datos cuando el código termine con él</span><span class="sxs-lookup"><span data-stu-id="b827e-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="b827e-106">Asegúrese de incluir la correspondiente [Imports (instrucción Namespace de .NET y tipo)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para la conexión de base de datos al principio del archivo de origen (en este caso, <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="b827e-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="b827e-107">Crear un `Using` bloque con el `Using` y `End Using` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b827e-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="b827e-108">Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b827e-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="b827e-109">Declare la conexión y cree una instancia de ella como parte de la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b827e-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="b827e-110">El sistema desecha el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="b827e-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="b827e-111">Tenga en cuenta que no se puede tener acceso a `sqc` desde fuera de la `Using` bloquear, porque su ámbito se limita al bloque.</span><span class="sxs-lookup"><span data-stu-id="b827e-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="b827e-112">Puede usar esta misma técnica en un recurso del sistema como un identificador de archivos o un contenedor COM.</span><span class="sxs-lookup"><span data-stu-id="b827e-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="b827e-113">Usa un `Using` bloquear cuando para asegurarse de que desea que deje el recurso disponible para otros componentes después de que haya salido el `Using` bloque.</span><span class="sxs-lookup"><span data-stu-id="b827e-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b827e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b827e-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="b827e-115">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="b827e-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="b827e-116">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="b827e-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="b827e-117">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="b827e-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="b827e-118">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="b827e-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="b827e-119">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="b827e-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="b827e-120">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b827e-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)

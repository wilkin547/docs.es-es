---
description: 'Más información acerca de cómo: desechar un recurso del sistema (Visual Basic)'
title: Procedimiento para deshacerse de un recurso del sistema
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: 6594c9e2eedf756cc7a46c2c17deab58fcba3a8c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480666"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="f9fc9-103">Cómo: Deshacerse de un recurso del sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9fc9-103">How to: Dispose of a System Resource (Visual Basic)</span></span>

<span data-ttu-id="f9fc9-104">Puede usar un `Using` bloque para garantizar que el sistema desecha un recurso cuando el código sale del bloque.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-104">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="f9fc9-105">Esto resulta útil si está utilizando un recurso del sistema que consume una gran cantidad de memoria, o que otros componentes también desean usar.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-105">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="f9fc9-106">Para eliminar una conexión de base de datos cuando el código finaliza con ella</span><span class="sxs-lookup"><span data-stu-id="f9fc9-106">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="f9fc9-107">Asegúrese de incluir la [instrucción Imports (espacio de nombres y tipo .net)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) adecuada para la conexión de base de datos al principio del archivo de código fuente (en este caso, <xref:System.Data.SqlClient> ).</span><span class="sxs-lookup"><span data-stu-id="f9fc9-107">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="f9fc9-108">Cree un `Using` bloque con las `Using` `End Using` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-108">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="f9fc9-109">Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-109">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="f9fc9-110">Declare la conexión y cree una instancia de ella como parte de la `Using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-110">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="f9fc9-111">El sistema desecha el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-111">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="f9fc9-112">Tenga en cuenta que no puede acceder `sqc` desde fuera del `Using` bloque, porque su ámbito está limitado al bloque.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-112">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="f9fc9-113">Puede usar esta misma técnica en un recurso del sistema, como un identificador de archivo o un contenedor COM.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-113">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="f9fc9-114">Puede usar un `Using` bloque cuando desee asegurarse de dejar el recurso disponible para otros componentes después de salir del `Using` bloque.</span><span class="sxs-lookup"><span data-stu-id="f9fc9-114">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fc9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9fc9-115">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="f9fc9-116">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="f9fc9-116">Control Flow</span></span>](index.md)
- [<span data-ttu-id="f9fc9-117">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="f9fc9-117">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="f9fc9-118">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="f9fc9-118">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="f9fc9-119">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="f9fc9-119">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="f9fc9-120">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="f9fc9-120">Nested Control Structures</span></span>](nested-control-structures.md)
- [<span data-ttu-id="f9fc9-121">Using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f9fc9-121">Using Statement</span></span>](../../../language-reference/statements/using-statement.md)

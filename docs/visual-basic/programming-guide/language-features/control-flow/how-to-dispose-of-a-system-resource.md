---
title: Procedimiento Eliminar un recurso de sistema (Visual Basic)
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
ms.openlocfilehash: 798650bbefc0c5b2ac097b87ab44a2b380117939
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523225"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Procedimiento Eliminar un recurso de sistema (Visual Basic)
Puede usar un `Using` bloque para garantizar que el sistema elimina un recurso al que el código sale del bloque. Esto es útil si está utilizando un recurso del sistema que consume una gran cantidad de memoria o que otros componentes que desee utilizar.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Para eliminar una conexión de base de datos cuando lo esté utilizando el código  
  
1.  Asegúrese de incluir la correspondiente [instrucción Imports (tipo y Namespace. NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para la conexión de base de datos al principio del archivo de origen (en este caso, <xref:System.Data.SqlClient>).  
  
2.  Crear un `Using` bloquear con el `Using` y `End Using` instrucciones. Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.  
  
3.  Declare la conexión y cree una instancia de ella como parte de la `Using` instrucción.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     El sistema elimina el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.  
  
     Tenga en cuenta que no se puede obtener acceso a `sqc` desde fuera de la `Using` block, porque su ámbito se limite al bloque.  
  
     Puede usar esta misma técnica en un recurso del sistema como un identificador de archivo o un contenedor COM. Usa un `Using` bloquear cuando para asegurarse de que desea que deje el recurso disponible para otros componentes una vez que haya salido el `Using` bloque.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Data.SqlClient.SqlConnection>
- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)

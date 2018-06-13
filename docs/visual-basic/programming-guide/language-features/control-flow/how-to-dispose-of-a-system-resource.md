---
title: 'Cómo: Deshacerse de un recurso del sistema (Visual Basic)'
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
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647236"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Cómo: Deshacerse de un recurso del sistema (Visual Basic)
Puede usar un `Using` bloque para garantizar que el sistema dispone de un recurso cuando el código sale del bloque. Esto es útil si está usando un recurso del sistema que consume una gran cantidad de memoria o que otros componentes también va a usar.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Para eliminar una conexión de base de datos cuando el código termine con él  
  
1.  Asegúrese de incluir la correspondiente [Imports (instrucción Namespace de .NET y tipo)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para la conexión de base de datos al principio del archivo de origen (en este caso, <xref:System.Data.SqlClient>).  
  
2.  Crear un `Using` bloque con el `Using` y `End Using` las instrucciones. Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.  
  
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
  
     El sistema desecha el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.  
  
     Tenga en cuenta que no se puede tener acceso a `sqc` desde fuera de la `Using` bloquear, porque su ámbito se limita al bloque.  
  
     Puede usar esta misma técnica en un recurso del sistema como un identificador de archivos o un contenedor COM. Usa un `Using` bloquear cuando para asegurarse de que desea que deje el recurso disponible para otros componentes después de que haya salido el `Using` bloque.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.SqlClient.SqlConnection>  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)

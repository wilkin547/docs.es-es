---
title: 'Cómo: Deshacerse de un recurso del sistema'
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
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353942"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Cómo: Deshacerse de un recurso del sistema (Visual Basic)
Puede usar un bloque `Using` para garantizar que el sistema desecha un recurso cuando el código sale del bloque. Esto resulta útil si está utilizando un recurso del sistema que consume una gran cantidad de memoria, o que otros componentes también desean usar.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Para eliminar una conexión de base de datos cuando el código finaliza con ella  
  
1. Asegúrese de incluir la [instrucción Imports (espacio de nombres y tipo .net)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) adecuada para la conexión de base de datos al principio del archivo de código fuente (en este caso, <xref:System.Data.SqlClient>).  
  
2. Cree un bloque `Using` con las instrucciones `Using` y `End Using`. Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.  
  
3. Declare la conexión y cree una instancia de ella como parte de la instrucción `Using`.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     El sistema desecha el recurso independientemente de cómo salga del bloque, incluido el caso de una excepción no controlada.  
  
     Tenga en cuenta que no puede tener acceso a `sqc` desde fuera del bloque de `Using`, porque su ámbito está limitado al bloque.  
  
     Puede usar esta misma técnica en un recurso del sistema, como un identificador de archivo o un contenedor COM. Use un bloque de `Using` cuando desee asegurarse de dejar el recurso disponible para otros componentes después de salir del bloque de `Using`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.SqlClient.SqlConnection>
- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using (instrucción)](../../../../visual-basic/language-reference/statements/using-statement.md)

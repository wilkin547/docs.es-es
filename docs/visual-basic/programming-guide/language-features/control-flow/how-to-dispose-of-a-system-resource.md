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
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Cómo: Deshacerse de un recurso del sistema (Visual Basic)

Puede usar un `Using` bloque para garantizar que el sistema desecha un recurso cuando el código sale del bloque. Esto resulta útil si está utilizando un recurso del sistema que consume una gran cantidad de memoria, o que otros componentes también desean usar.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Para eliminar una conexión de base de datos cuando el código finaliza con ella  
  
1. Asegúrese de incluir la [instrucción Imports (espacio de nombres y tipo .net)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) adecuada para la conexión de base de datos al principio del archivo de código fuente (en este caso, <xref:System.Data.SqlClient> ).  
  
2. Cree un `Using` bloque con las `Using` `End Using` instrucciones y. Dentro del bloque, coloque el código que se ocupa de la conexión de base de datos.  
  
3. Declare la conexión y cree una instancia de ella como parte de la `Using` instrucción.  
  
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
  
     Tenga en cuenta que no puede acceder `sqc` desde fuera del `Using` bloque, porque su ámbito está limitado al bloque.  
  
     Puede usar esta misma técnica en un recurso del sistema, como un identificador de archivo o un contenedor COM. Puede usar un `Using` bloque cuando desee asegurarse de dejar el recurso disponible para otros componentes después de salir del `Using` bloque.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.SqlClient.SqlConnection>
- [Flujo de control](index.md)
- [Estructuras de decisión](decision-structures.md)
- [Estructuras de bucle](loop-structures.md)
- [Estructuras de control adicionales](other-control-structures.md)
- [Estructuras de control anidadas](nested-control-structures.md)
- [Using (instrucción)](../../../language-reference/statements/using-statement.md)

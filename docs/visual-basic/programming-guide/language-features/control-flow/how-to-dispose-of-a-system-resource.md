---
title: "C&#243;mo: Deshacerse de un recurso del sistema (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "recursos [Visual Basic], desechar el sistema"
  - "recursos del sistema"
  - "recursos del sistema, desechar"
  - "Using (bloque)"
  - "Using (instrucción), desechar recursos del sistema"
  - "Using (instrucción), Using...End Using"
  - "código de Visual Basic, flujo de control"
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Deshacerse de un recurso del sistema (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede utilizar un bloque `Using` para garantizar que el sistema desecha un recurso cuando su código sale del bloque.  Esto es útil si está empleando un recurso del sistema que utiliza una gran cantidad de memoria o que otros componentes también desean utilizar.  
  
### Para desechar una conexión a bases de datos cuando su código haya acabado de usarla  
  
1.  Asegúrese de que incluye la instrucción [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) apropiada para la conexión a bases de datos al principio del archivo de código fuente \(en este caso, <xref:System.Data.SqlClient>\).  
  
2.  Cree un bloque `Using` con las instrucciones `Using` y `End Using`.  Coloque el código que trata la conexión a bases de datos dentro del bloque.  
  
3.  Declare la conexión y cree una instancia de ella como parte de la instrucción `Using`.  
  
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
  
     Tenga en cuenta que no puede tener acceso a `sqc` desde fuera del bloque `Using` porque su ámbito se limita al bloque.  
  
     Puede utilizar esta misma técnica en un recurso del sistema como un identificador de archivos o un contenedor COM.  Utilice un bloque `Using` cuando desee dejar el recurso disponible para otros componentes después de haber salido del bloque `Using`.  
  
## Vea también  
 <xref:System.Data.SqlClient.SqlConnection>   
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Estructuras de bucles](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using \(Instrucción\)](../../../../visual-basic/language-reference/statements/using-statement.md)
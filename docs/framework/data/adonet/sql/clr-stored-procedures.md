---
title: "Procedimientos almacenados CLR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Procedimientos almacenados CLR
Los procedimientos almacenados son rutinas que no se pueden utilizar en expresiones escalares.  Pueden devolver resultados en tabla y mensajes al cliente, invocar instrucciones de lenguaje de definición de datos \(DDL\) y lenguaje de manipulación de datos \(DML\) y devolver parámetros de salida.  
  
> [!NOTE]
>  Microsoft Visual Basic no admite parámetros de salida de la misma forma que Microsoft Visual C\#.  Deberá especificar que se pase el parámetro por referencia y aplicar el atributo \<Out\(\)\> para representar el parámetro de salida, como se muestra a continuación:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1.  [Procedimientos almacenados de CLR](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## Vea también  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/es-es/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)
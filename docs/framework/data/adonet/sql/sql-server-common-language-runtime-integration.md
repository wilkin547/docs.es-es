---
title: "Integraci&#243;n de Common Language Runtime de SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Integraci&#243;n de Common Language Runtime de SQL Server
SQL Server 2005 introdujo la integración del componente Common Language Runtime \(CLR\) de .NET Framework para Microsoft Windows.  Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C\#.  El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones \(API\) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.  
  
 En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime \(CLR\) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.  
  
 El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.  Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1.  [Conceptos de programación en el ámbito de la integración de Common Language Runtime \(CLR\)](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## En esta sección  
 [Introducción a la integración CLR de SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Proporciona una introducción a la integración CLR de SQL Server.  También proporciona vínculos a temas adicionales.  
  
 [Funciones CLR definidas por el usuario](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Describe cómo implementar y utilizar los diferentes tipos de funciones CLR: con valores de tabla, escalares y funciones de agregado definidas por el usuario.  
  
 [Tipos CLR definidos por el usuario](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Describe cómo implementar y utilizar tipos definidos por el usuario CLR.  También proporciona vínculos a temas adicionales.  
  
 [Procedimientos almacenados CLR](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Describe cómo implementar y utilizar procedimientos almacenados CLR.  También proporciona vínculos a temas adicionales.  
  
 [Desencadenadores CLR](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Describe cómo implementar y utilizar desencadenadores CLR.  También proporciona vínculos a temas adicionales.  
  
 [La conexión de contexto](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Describe la conexión de contexto.  
  
 [Comportamiento específico en proceso de SQL Server de ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto.  También proporciona vínculos a temas adicionales.  
  
## Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/es-es/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)
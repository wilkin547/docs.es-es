---
title: "SQL Server Compact y LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL Server Compact y LINQ to SQL
SQL Server Compact es la base de datos predeterminada instala con Visual Studio. Para obtener más información, vea [PAVE OVER Using SQL Server Compact \(Visual Studio\)](http://msdn.microsoft.com/es-es/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 En este tema se describen las diferencias fundamentales en cuanto a uso, configuración, conjuntos de características y ámbito de compatibilidad con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## Características de SQL Server Compact en relación con LINQ to SQL  
 De forma predeterminada, SQL Server Compact se instala para todas las ediciones de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] y, por lo tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Sin embargo, la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] es distinta de la de una aplicación de [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].  SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.  
  
 Observe las siguientes características:  
  
-   SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos \(extensión .sdf\).  
  
-   SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente.  Por lo tanto, la eficacia de la comunicación con SQL Server Compact puede ser significativamente mayor que con [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].  Por otro lado, SQL Server Compact necesita interoperabilidad entre el código administrado y no administrado, con el costo que ello implica.  
  
-   El tamaño del archivo DLL de SQL Server Compact es pequeño.  Esta característica reduce el tamaño total de la aplicación.  
  
-   El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] no admite SQL Server Compact.  
  
## Conjunto de características  
 El conjunto de características de SQL Server Compact es mucho más sencillo que el de [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] en los aspectos siguientes, que pueden afectar a las aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
-   SQL Server Compact no admite las vistas ni los procedimientos almacenados.  
  
-   SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.  
  
-   SQL Server Compact admite solo un subconjunto de construcciones de SQL.  
  
-   SQL Server Compact proporciona solo un optimizador mínimo.  Es posible que algunas consultas agoten el tiempo de espera.  
  
-   SQL Server Compact no admite la confianza parcial.  
  
## Vea también  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
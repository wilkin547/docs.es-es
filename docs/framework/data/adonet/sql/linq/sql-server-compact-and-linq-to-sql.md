---
title: SQL Server Compact y LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 24f620319cd469538cf4454be7caffececdf9213
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact y LINQ to SQL
SQL Server Compact es la base de datos predeterminado instalado con Visual Studio. Para obtener más información, consulte [PAVE sobre uso de SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 En este tema se describe las diferencias claves en uso, configuración, conjuntos de características y ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Características de SQL Server Compact en relación con LINQ to SQL  
 De forma predeterminada, SQL Server Compact se instala para todos los [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] ediciones y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de la de un [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] aplicación. SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.  
  
 Observe las siguientes características:  
  
-   SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).  
  
-   SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente. La eficacia de la comunicación con SQL Server Compact, por tanto, puede ser significativamente mayor que con [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]. Por otro lado, SQL Server Compact necesita interoperabilidad entre código administrado y con su costo que ello implica.  
  
-   El tamaño de la DLL de SQL Server Compact es pequeño. Esta característica reduce el tamaño total de la aplicación.  
  
-   El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] no admite SQL Server Compact.  
  
## <a name="feature-set"></a>Conjunto de características  
 El conjunto de características de SQL Server Compact es mucho más sencillo que el conjunto de características de [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] de las maneras siguientes que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplicaciones:  
  
-   SQL Server Compact no admite las vistas ni los procedimientos almacenados.  
  
-   SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.  
  
-   SQL Server Compact admite solo un subconjunto de construcciones de SQL.  
  
-   SQL Server Compact proporciona solo un optimizador mínimo. Es posible que algunas consultas es posible que el tiempo de espera.  
  
-   SQL Server Compact no admite la confianza parcial.  
  
## <a name="see-also"></a>Vea también  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)

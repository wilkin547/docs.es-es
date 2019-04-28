---
title: SQL Server Compact y LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: db3f7aef082d965dc27b69f5a966ff038c0ffac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917857"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact y LINQ to SQL
SQL Server Compact es la base de datos predeterminada instalada con Visual Studio. Para obtener más información, consulte [utilizando SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 Este tema describen las diferencias clave en uso, configuración, conjuntos de características y ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Características de SQL Server Compact en relación con LINQ to SQL  
 De forma predeterminada, SQL Server Compact se instala para todas las ediciones de Visual Studio y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de una aplicación de SQL Server. SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.  
  
 Observe las siguientes características:  
  
- SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).  
  
- SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente. La eficacia de la comunicación con SQL Server Compact, por tanto, puede ser significativamente mayor que con SQL Server. Por otro lado, SQL Server Compact necesita interoperabilidad entre código administrado y con su costo que ello implica.  
  
- El tamaño de la DLL de SQL Server Compact es pequeño. Esta característica reduce el tamaño total de la aplicación.  
  
- El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.  
  
- [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] no admite SQL Server Compact.  
  
## <a name="feature-set"></a>Conjunto de características  
 El conjunto de características de SQL Server Compact es mucho más sencillo que el conjunto de características de SQL Server de las maneras siguientes que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplicaciones:  
  
- SQL Server Compact no admite las vistas ni los procedimientos almacenados.  
  
- SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.  
  
- SQL Server Compact admite solo un subconjunto de construcciones de SQL.  
  
- SQL Server Compact proporciona solo un optimizador mínimo. Es posible que algunas consultas, es posible que el tiempo de espera.  
  
- SQL Server Compact no admite la confianza parcial.  
  
## <a name="see-also"></a>Vea también

- [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)

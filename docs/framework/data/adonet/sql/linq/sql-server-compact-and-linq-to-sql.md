---
title: SQL Server Compact y LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: bdd1237a8eac1c278e7704f3fbf0ae8b1deeff42
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541368"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact y LINQ to SQL
SQL Server Compact es la base de datos predeterminada instalada con Visual Studio. Para obtener más información, vea [uso de SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 En este tema se describen las principales diferencias en el uso, la configuración, los conjuntos de características y el ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soporte técnico.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Características de SQL Server Compact en relación con LINQ to SQL  
 De forma predeterminada, SQL Server Compact se instala para todas las ediciones de Visual Studio y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de la de una aplicación SQL Server. SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.  
  
 Observe las siguientes características:  
  
- SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).  
  
- SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente. Por lo tanto, la eficacia de la comunicación con SQL Server Compact puede ser mucho mayor que la comunicación con SQL Server. Por otro lado, SQL Server Compact necesita interoperabilidad entre el código administrado y no administrado, con el costo que ello implica.  
  
- El tamaño del archivo DLL de SQL Server Compact es pequeño. Esta característica reduce el tamaño total de la aplicación.  
  
- El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.  
  
- El Object Relational Designer no admite SQL Server Compact.  
  
## <a name="feature-set"></a>Conjunto de características  
 El conjunto de características SQL Server Compact es mucho más sencillo que el conjunto de características de SQL Server de las siguientes maneras que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones:  
  
- SQL Server Compact no admite las vistas ni los procedimientos almacenados.  
  
- SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.  
  
- SQL Server Compact admite solo un subconjunto de construcciones de SQL.  
  
- SQL Server Compact proporciona solo un optimizador mínimo. Es posible que algunas consultas agoten el tiempo de espera.  
  
- SQL Server Compact no admite la confianza parcial.  
  
## <a name="see-also"></a>Vea también

- [Referencia](reference.md)

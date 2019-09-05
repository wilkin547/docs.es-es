---
title: Generación de SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 2c18e88967fcba2b8414bfc171412eba908002b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248400"
---
# <a name="sql-generation"></a>Generación de SQL
Al escribir un proveedor para [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], debe traducir los árboles de comandos de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] en SQL que una base de datos concreta puede entender, como Transact-SQL para SQL Server o PL/SQL para Oracle. En esta sección, obtendrá información sobre cómo desarrollar un componente de generación de SQL (para consultas SELECT) para un proveedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener información sobre las consultas de inserción, actualización y eliminación, vea modificación de la [generación de SQL](modification-sql-generation.md).  
  
 Para entender esta sección, debe estar familiarizado con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y el modelo de proveedor de ADO.NET. También debe comprender los árboles de comandos y <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>El rol del módulo de generación de SQL  
 El módulo de generación de SQL de un proveedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] traduce un árbol de comandos de consulta determinado en una instrucción SELECT de SQL única que tiene como destino una base de datos conforme a SQL:1999. El SQL generado debe tener el menor número posible de consultas anidadas. El módulo de generación de SQL no debe simplificar el árbol de comandos de consulta de salida. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] se encargará de hacerlo, por ejemplo mediante la eliminación de combinaciones y la contracción de nodos de filtro consecutivos.  
  
 La clase <xref:System.Data.Common.DbProviderServices> es el punto inicial para tener acceso al nivel de generación de SQL para convertir árboles de comandos en <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Forma de los árboles de comandos](the-shape-of-the-command-trees.md)  
  
 [Generación de SQL a partir de árboles de comandos: procedimientos recomendados](generating-sql-from-command-trees-best-practices.md)  
  
 [Generación de SQL en el proveedor de ejemplo](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Vea también

- [Escritura de un proveedor de datos de Entity Framework](writing-an-ef-data-provider.md)

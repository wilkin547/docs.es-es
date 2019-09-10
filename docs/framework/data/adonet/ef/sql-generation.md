---
title: Generación de SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854357"
---
# <a name="sql-generation"></a>Generación de SQL
Al escribir un proveedor para el Entity Framework, debe traducir Entity Framework árboles de comandos en SQL que una base de datos concreta pueda comprender, como Transact-SQL para SQL Server o PL/SQL para Oracle. En esta sección, obtendrá información sobre cómo desarrollar un componente de generación de SQL (para consultas SELECT) para un proveedor de Entity Framework. Para obtener información sobre las consultas de inserción, actualización y eliminación, vea modificación de la [generación de SQL](modification-sql-generation.md).  
  
 Para entender esta sección, debe estar familiarizado con el Entity Framework y el modelo de proveedor ADO.NET. También debe comprender los árboles de comandos y <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>El rol del módulo de generación de SQL  
 El módulo de generación de SQL de un proveedor de Entity Framework traduce un árbol de comandos de consulta determinado en una única instrucción SELECT de SQL que tiene como destino una base de datos compatible con SQL: 1999. El SQL generado debe tener el menor número posible de consultas anidadas. El módulo de generación de SQL no debe simplificar el árbol de comandos de consulta de salida. El Entity Framework hará esto, por ejemplo, eliminando combinaciones y contraiga nodos de filtro consecutivos.  
  
 La clase <xref:System.Data.Common.DbProviderServices> es el punto inicial para tener acceso al nivel de generación de SQL para convertir árboles de comandos en <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Forma de los árboles de comandos](the-shape-of-the-command-trees.md)  
  
 [Generación de SQL a partir de árboles de comandos: procedimientos recomendados](generating-sql-from-command-trees-best-practices.md)  
  
 [Generación de SQL en el proveedor de ejemplo](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Vea también

- [Escritura de un proveedor de datos de Entity Framework](writing-an-ef-data-provider.md)

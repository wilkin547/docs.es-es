---
title: Generación de SQL en el proveedor de ejemplo
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: d0e058cdc4dd3f7a1a04ab6eea5acf4d3deabb89
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248505"
---
# <a name="sql-generation-in-the-sample-provider"></a>Generación de SQL en el proveedor de ejemplo
En el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) se muestran los nuevos componentes de los proveedores de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]datos de ADO.net que admiten.  Funciona con una base de datos SQL Server 2005 y se implementa como un contenedor del proveedor de datos ADO.NET 2.0 System.Data.SqlClient.  
  
 El módulo Generación de SQL del proveedor de ejemplo (ubicado en la carpeta Generación de SQL, salvo el archivo DmlSqlGenerator.cs) toma una entrada DbQueryCommandTree y genera una instrucción SQL SELECT única.  
  
## <a name="in-this-section"></a>En esta sección  
 Esta sección contiene los siguientes temas:  
  
 [Arquitectura y diseño](architecture-and-design.md)  
  
 [Tutorial: Generación de SQL](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Vea también

- [Generación de SQL](sql-generation.md)

---
title: "Generación de SQL en el proveedor de ejemplo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 853bf55f96be3adeba11ff14e36fd56631536b69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sql-generation-in-the-sample-provider"></a>Generación de SQL en el proveedor de ejemplo
El [proveedor de ejemplo de Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) muestra los nuevos componentes de proveedores de datos de ADO.NET que admiten la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Funciona con una base de datos SQL Server 2005 y se implementa como un contenedor del proveedor de datos ADO.NET 2.0 System.Data.SqlClient.  
  
 El módulo Generación de SQL del proveedor de ejemplo (ubicado en la carpeta Generación de SQL, salvo el archivo DmlSqlGenerator.cs) toma una entrada DbQueryCommandTree y genera una instrucción SQL SELECT única.  
  
## <a name="in-this-section"></a>En esta sección  
 Esta sección contiene los siguientes temas:  
  
 [Arquitectura y diseño](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [Tutorial: generación de SQL](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Vea también  
 [Generación de SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)

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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7a7f95f7432fdac00a34e7d878ef979656a7af4e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
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

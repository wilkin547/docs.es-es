---
title: Generación de SQL en el proveedor de ejemplo
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854320"
---
# <a name="sql-generation-in-the-sample-provider"></a>Generación de SQL en el proveedor de ejemplo
En el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) se muestran los nuevos componentes de los proveedores de datos de ADO.net que admiten el Entity Framework.  Funciona con una base de datos SQL Server 2005 y se implementa como un contenedor del proveedor de datos ADO.NET 2.0 System.Data.SqlClient.  
  
 El módulo Generación de SQL del proveedor de ejemplo (ubicado en la carpeta Generación de SQL, salvo el archivo DmlSqlGenerator.cs) toma una entrada DbQueryCommandTree y genera una instrucción SQL SELECT única.  
  
## <a name="in-this-section"></a>En esta sección  
 Esta sección contiene los siguientes temas:  
  
 [Arquitectura y diseño](architecture-and-design.md)  
  
 [Tutorial: Generación de SQL](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>Vea también

- [Generación de SQL](sql-generation.md)

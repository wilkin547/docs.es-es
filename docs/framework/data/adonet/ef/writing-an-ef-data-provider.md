---
title: Escribir un proveedor de datos de Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854163"
---
# <a name="writing-an-entity-framework-data-provider"></a>Escribir un proveedor de datos de Entity Framework
En esta sección se explica cómo escribir un proveedor de Entity Framework para admitir un origen de datos que no sea SQL Server. El Entity Framework incluye un proveedor que admite SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Introducción al modelo de proveedor de Entity Framework  
 El Entity Framework es independiente de la base de datos y puede escribir un proveedor mediante el modelo de proveedor ADO.NET para conectarse a un conjunto diverso de orígenes de datos.  
  
 El proveedor de datos de Entity Framework (compilado mediante el modelo de proveedor de datos de ADO.NET) realiza las siguientes funciones:  
  
- Asigna los tipos primitivos de Entity Data Model (EDM) a los tipos de proveedor.  
  
- Expone funciones específicas del proveedor.  
  
- Genera comandos específicos del proveedor para que un DbQueryCommandTree determinado admita consultas Entity Framework.  
  
- Genera comandos de actualización específicos del proveedor para que un DbModificationCommandTree determinado admita actualizaciones a través de la Entity Framework.  
  
- Expone archivos de asignación para la definición de esquema de almacenamiento, para admitir la generación de un modelo basado en una base de datos.  
  
- Expone metadatos (tablas y vistas, por ejemplo) a través de un modelo conceptual.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Muestra  
 Vea el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) para obtener un ejemplo de un proveedor de Entity Framework que admite un origen de datos distinto de SQL Server.  
  
## <a name="in-this-section"></a>En esta sección  
 [Generación de SQL](sql-generation.md)  
  
 [Generación de SQL de modificación](modification-sql-generation.md)  
  
 [Especificación del manifiesto del proveedor](provider-manifest-specification.md)  
  
## <a name="see-also"></a>Vea también

- [Trabajo con proveedores de datos](working-with-data-providers.md)

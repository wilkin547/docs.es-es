---
title: Escribir un proveedor de datos de Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 6c5e6e2859b48db6c982862381d223a4c9deb2c5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248189"
---
# <a name="writing-an-entity-framework-data-provider"></a>Escribir un proveedor de datos de Entity Framework
En esta sección se explica cómo escribir un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proveedor de para admitir un origen de datos que no sea SQL Server. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Incluye un proveedor que admite SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Introducción al modelo de proveedor de Entity Framework  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es independiente de la base de datos, por lo que puede escribir un proveedor utilizando el modelo de proveedor de ADO.NET para conectar a un conjunto diverso de orígenes de datos.  
  
 El proveedor de datos de Entity Framework (compilado mediante el modelo de proveedor de datos de ADO.NET) realiza las siguientes funciones:  
  
- Asigna los tipos primitivos de Entity Data Model (EDM) a los tipos de proveedor.  
  
- Expone funciones específicas del proveedor.  
  
- Genera comandos específicos del proveedor para que un elemento DbQueryCommandTree determinado admita consultas de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
- Genera comandos de actualización específicos del proveedor para que un elemento DbModificationCommandTree determinado admita las actualizaciones a través de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
- Expone archivos de asignación para la definición de esquema de almacenamiento, para admitir la generación de un modelo basado en una base de datos.  
  
- Expone metadatos (tablas y vistas, por ejemplo) a través de un modelo conceptual.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Muestra  
 Vea el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) para obtener un ejemplo [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] de un proveedor que admite un origen de datos que no sea SQL Server.  
  
## <a name="in-this-section"></a>En esta sección  
 [Generación de SQL](sql-generation.md)  
  
 [Generación de SQL de modificación](modification-sql-generation.md)  
  
 [Especificación del manifiesto del proveedor](provider-manifest-specification.md)  
  
## <a name="see-also"></a>Vea también

- [Trabajo con proveedores de datos](working-with-data-providers.md)

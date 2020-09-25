---
title: Funciones (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201075"
---
# <a name="functions-entity-sql"></a>Funciones (Entity SQL)

Entity SQL admite funciones definidas por el usuario, funciones canónicas y funciones específicas del proveedor. Las funciones definidas por el usuario se especifican en el modelo conceptual o inline en la consulta. Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).  
  
 Las funciones canónicas se predefinen en el Entity Framework y los proveedores de datos las admiten. Se producirá un error en los comandos de Entity SQL si un usuario llama a una función que un proveedor no admita. Por consiguiente, las funciones canónicas generalmente se recomiendan sobre las funciones específicas del proveedor, que están en un espacio de nombres concreto del proveedor. Para obtener más información, vea [funciones canónicas](canonical-functions.md).  
  
 El proveedor administrado de Microsoft SQL Client proporciona un conjunto de funciones específicas del proveedor. Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Funciones definidas por el usuario](user-defined-functions-entity-sql.md)  
  
 [Resolución de la sobrecarga de funciones](function-overload-resolution-entity-sql.md)  
  
 [Funciones de agregado](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre Entity SQL](entity-sql-overview.md)

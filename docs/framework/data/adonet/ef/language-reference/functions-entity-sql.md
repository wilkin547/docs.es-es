---
title: Funciones (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb55fecc7c876fda5918418e353eaf327ce6c034
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="functions-entity-sql"></a>Funciones (Entity SQL)
Entity SQL admite funciones definidas por el usuario, funciones canónicas y funciones específicas del proveedor. Las funciones definidas por el usuario se especifican en el modelo conceptual o inline en la consulta. Para obtener más información, consulte [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
 Las funciones canónicas se predefinen en el Entity Framework y los proveedores de datos las admiten. Se producirá un error en los comandos de Entity SQL si un usuario llama a una función que un proveedor no admita. Por consiguiente, las funciones canónicas generalmente se recomiendan sobre las funciones específicas del proveedor, que están en un espacio de nombres concreto del proveedor. Para obtener más información, consulte [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
 El proveedor administrado de Microsoft SQL Client proporciona un conjunto de funciones específicas del proveedor. Para obtener más información, consulte [SqlClient para Entity Framework funciones](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Funciones definidas por el usuario](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [Resolución de sobrecarga (función)](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [Funciones de agregado](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

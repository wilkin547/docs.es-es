---
description: Más información acerca de:. (Acceso a miembros) (Entity SQL)
title: . (Acceso a miembros) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 94833d3525c7d17cadaef15065b3dcbdb43a6ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739383"
---
# <a name="-member-access-entity-sql"></a>. (Acceso a miembros) (Entity SQL)

El operador punto (.) es el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operador de acceso a miembros. El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Instancia de un tipo del modelo conceptual estructural.  
  
 `identifier`  
 Propiedad o campo que pertenece a una instancia de objeto.  
  
## <a name="remarks"></a>Observaciones  

 El operador punto (.) se puede utilizar para extraer campos de un registro, que es similar a extraer propiedades de un tipo complejo o de entidad. Por ejemplo, si n de tipo Name de tipo es miembro de tipo Person, y p es una instancia de tipo Person, p.n es una expresión de acceso a miembros legal que obtiene un valor de tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)

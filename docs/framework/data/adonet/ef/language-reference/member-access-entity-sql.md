---
title: . (Acceso a miembros) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 1db6be632da90eaa7a761bb213e395182ae42347
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250295"
---
# <a name="-member-access-entity-sql"></a>. (Acceso a miembros) (Entity SQL)
El operador punto (.) es el [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operador de acceso a miembros. El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Instancia de un tipo del modelo conceptual estructural.  
  
 `identifier`  
 Propiedad o campo que pertenece a una instancia de objeto.  
  
## <a name="remarks"></a>Comentarios  
 El operador punto (.) se puede utilizar para extraer campos de un registro, que es similar a extraer propiedades de un tipo complejo o de entidad. Por ejemplo, si n de tipo Name de tipo es miembro de tipo Person, y p es una instancia de tipo Person, p.n es una expresión de acceso a miembros legal que obtiene un valor de tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)

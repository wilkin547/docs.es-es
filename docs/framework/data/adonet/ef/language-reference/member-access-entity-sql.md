---
title: . (Acceso a miembros) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 8e63caba9e9efb91d5c4629b9da0b1feca905ace
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319651"
---
# <a name="-member-access-entity-sql"></a>. (Acceso a miembros) (Entity SQL)
El operador punto (.) es el operador de acceso a miembros [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. El operador de acceso a miembros se usa para obtener el valor de una propiedad o un campo de una instancia de un tipo del modelo conceptual estructural.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
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

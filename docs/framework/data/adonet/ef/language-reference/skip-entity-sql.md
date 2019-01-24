---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 467329f74304b64c7fc7ada2920751aba744f76e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637643"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)
Puede realizar la paginación física utilizando la subcláusula SKIP en la cláusula ORDER BY. SKIP no se puede utilizar por separado de la cláusula ORDER BY.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `n`  
 Número de elementos que se han de omitir.  
  
## <a name="remarks"></a>Comentarios  
 Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP. Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.  
  
> [!NOTE]
>  Una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se no es válida si tanto el modificador TOP como la subcláusula SKIP están presentes en la misma expresión de consulta. La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.  
  
> [!NOTE]
>  En [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], el uso de SKIP con ORDER BY en columnas sin clave puede hacer que los resultados devueltos sean incorrectos. Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella. Esto se debe a cómo se convierte SKIP en [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Por ejemplo, en el código siguiente se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 La consulta de  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en [este](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) ejemplo, usa el operador ORDER BY con SKIP para especificar el criterio de ordenación que se usa en los objetos devueltos en una instrucción SELECT.  
  
## <a name="see-also"></a>Vea también
- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Cómo: Página de resultados de la consulta](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
- [Paginación](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)

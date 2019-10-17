---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 75140384823588b8f6785de00b0ab3cd17314a3f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319340"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)

Puede realizar la paginación física utilizando la subcláusula SKIP en la cláusula ORDER BY. SKIP no se puede utilizar por separado de la cláusula ORDER BY.

## <a name="syntax"></a>Sintaxis

```sql
[ SKIP n ]
```

## <a name="arguments"></a>Argumentos

`n` \
Número de elementos que se han de omitir.

## <a name="remarks"></a>Comentarios

Si en una cláusula ORDER BY hay una subcláusula de expresión SKIP, los resultados se ordenarán en función de la especificación de clasificación, y el conjunto de resultados incluirá filas a partir de la situada inmediatamente después de la expresión SKIP. Por ejemplo, SKIP 5 omitirá las cinco primeras filas y devolverá a partir de la sexta.

> [!NOTE]
> Una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se no es válida si tanto el modificador TOP como la subcláusula SKIP están presentes en la misma expresión de consulta. La consulta se debe volver a escribir cambiando la expresión TOP a la expresión LIMIT.

> [!NOTE]
> En SQL Server 2000, el uso de SKIP con ORDER BY en columnas que no son de clave puede devolver resultados incorrectos. Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella. Esto se debe a la forma en que se traduce SKIP para SQL Server 2000. Por ejemplo, en el código siguiente se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en [Cómo: paginar a través de los resultados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) de la consulta usa el operador order by con SKIP para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.

## <a name="see-also"></a>Vea también

- [ORDER BY](order-by-entity-sql.md)
- [Cómo: paginar a través de los resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paginación](paging-entity-sql.md)
- [TOP](top-entity-sql.md)

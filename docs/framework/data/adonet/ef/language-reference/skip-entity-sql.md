---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 19d3001fb8f226b02f16167dfb51ce1caa80ba3b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249217"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)

Puede realizar la paginación física utilizando la subcláusula SKIP en la cláusula ORDER BY. SKIP no se puede utilizar por separado de la cláusula ORDER BY.

## <a name="syntax"></a>Sintaxis

```
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
> `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`

La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta en [cómo: La página a través](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) de los resultados de la consulta utiliza el operador order by con SKIP para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.

## <a name="see-also"></a>Vea también

- [ORDER BY](order-by-entity-sql.md)
- [Procedimientos: Página a través de los resultados de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paginación](paging-entity-sql.md)
- [TOP](top-entity-sql.md)

---
description: 'Más información acerca de: definición de esquema DataTable'
title: Definición del esquema de DataTable
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: b1a48c8a129607dc8d683aa4735ea0e86ed32cc2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652619"
---
# <a name="datatable-schema-definition"></a>Definición del esquema de DataTable

El esquema, o estructura, de una tabla se representa con columnas y restricciones. El esquema de una <xref:System.Data.DataTable> se define mediante objetos <xref:System.Data.DataColumn>, <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Las referencias a los nombres de columnas, relaciones y restricciones de una tabla hacen distinción entre mayúsculas y minúsculas. En una tabla puede haber dos o más columnas, relaciones y restricciones con el mismo nombre, pero con distinción entre mayúsculas y minúsculas. Por ejemplo, puede tener **col1** y **col1**. En este caso, una referencia al nombre de una de las columnas tiene que coincidir exactamente con las mayúsculas y minúsculas del nombre de la columna, de lo contrario se inicia una excepción. Por ejemplo, si **la tabla MyTable contiene las** columnas **col1** y **col1**, haría referencia a **col1** por nombre como **MyTable. Columns ["col1"]** y **col1** como **MyTable. Columns ["col1"]**. Al intentar hacer referencia a cualquiera de las columnas como **MyTable. Columns ["col1"]** se generaría una excepción.  
  
 La regla de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una columna, relación o restricción con un nombre concreto. Es decir, si no hay ningún otro objeto de columna, relación o restricción en la tabla que coincida con el nombre de ese objeto de columna, relación o restricción concreto, se puede hacer referencia al nombre del objeto utilizando cualquier mayúscula o minúscula y no se generará una excepción. Por ejemplo, si la tabla solo tiene **col1**, puede hacer referencia a ella mediante **My. Columns ["COL1"]**.  
  
> [!NOTE]
> La <xref:System.Data.DataTable.CaseSensitive%2A> propiedad de la **DataTable** no afecta a este comportamiento. La propiedad **CaseSensitive** se aplica a los datos de una tabla y afecta a la ordenación, la búsqueda, el filtrado, la aplicación de restricciones, etc., pero no las referencias a las columnas, relaciones y restricciones.  
  
## <a name="in-this-section"></a>En esta sección  

 [Agregar columnas a un objeto DataTable](adding-columns-to-a-datatable.md)  
 Describe cómo definir las columnas de una tabla mediante objetos **DataColumn** .  
  
 [Crear columnas de expresión](creating-expression-columns.md)  
 Explica cómo se puede usar la propiedad **Expression** de una columna para calcular valores en función de los valores de otras columnas de la fila.  
  
 [Crear columnas de incremento automático](creating-autoincrement-columns.md)  
 Describe cómo se puede establecer una columna para que incremente automáticamente los valores numéricos y, así, se garantice un valor de columna exclusivo por fila.  
  
 [Definir claves principales](defining-primary-keys.md)  
 Describe cómo especificar la clave principal de una tabla a partir de uno o más objetos **DataColumn** .  
  
 [Restricciones de DataTable](datatable-constraints.md)  
 Describe cómo se define una clave externa y restricciones UNIQUE para las columnas de una tabla.  
  
## <a name="see-also"></a>Vea también

- [Objetos DataTable](datatables.md)
- [Información general de ADO.NET](../ado-net-overview.md)

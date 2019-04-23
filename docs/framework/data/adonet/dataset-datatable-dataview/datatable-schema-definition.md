---
title: Definición del esquema de DataTable
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: e8710e7d92558f525a6feaedf8d0635c5ce6e2c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163077"
---
# <a name="datatable-schema-definition"></a>Definición del esquema de DataTable
El esquema, o estructura, de una tabla se representa con columnas y restricciones. El esquema de una <xref:System.Data.DataTable> se define mediante objetos <xref:System.Data.DataColumn>, <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Las referencias a los nombres de columnas, relaciones y restricciones de una tabla hacen distinción entre mayúsculas y minúsculas. En una tabla puede haber dos o más columnas, relaciones y restricciones con el mismo nombre, pero con distinción entre mayúsculas y minúsculas. Por ejemplo, puede tener **Col1** y **col1**. En este caso, una referencia al nombre de una de las columnas tiene que coincidir exactamente con las mayúsculas y minúsculas del nombre de la columna, de lo contrario se inicia una excepción. Por ejemplo, si la tabla **myTable** contiene las columnas **Col1** y **col1**, podría hacer referencia **Col1** por su nombre como  **myTable.Columns["Col1"]**, y **col1** como **myTable.Columns["col1"]**. Al intentar hacer referencia a cualquiera de las columnas como **myTable.Columns["COL1"]** generaría una excepción.  
  
 La regla de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una columna, relación o restricción con un nombre concreto. Es decir, si no hay ningún otro objeto de columna, relación o restricción en la tabla que coincida con el nombre de ese objeto de columna, relación o restricción concreto, se puede hacer referencia al nombre del objeto utilizando cualquier mayúscula o minúscula y no se generará una excepción. Por ejemplo, si la tabla tiene solo **Col1**, puede hacer referencia a ella mediante **mi. Columnas ["COL1"]**.  
  
> [!NOTE]
>  El <xref:System.Data.DataTable.CaseSensitive%2A> propiedad de la **DataTable** no afecta a este comportamiento. El **CaseSensitive** propiedad se aplica a los datos en una tabla y afecta a ordenar, buscar, filtrar, aplicar las restricciones etc., pero no a las referencias a las columnas, relaciones y restricciones.  
  
## <a name="in-this-section"></a>En esta sección  
 [Adición de columnas a un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Describe cómo definir las columnas de una tabla con **DataColumn** objetos.  
  
 [Creación de columnas de expresión](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Explica cómo el **expresión** propiedad de una columna puede usarse para calcular valores basados en los valores de otras columnas de la fila.  
  
 [Creación de columnas de incremento automático](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Describe cómo se puede establecer una columna para que incremente automáticamente los valores numéricos y, así, se garantice un valor de columna exclusivo por fila.  
  
 [Definición de claves principales](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Describe cómo especificar la clave principal de una tabla de uno o varios **DataColumn** objetos.  
  
 [Restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Describe cómo se define una clave externa y restricciones UNIQUE para las columnas de una tabla.  
  
## <a name="see-also"></a>Vea también

- [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

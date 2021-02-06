---
description: Más información acerca de cómo combinar el contenido de un conjunto de DataSet
title: Combinar contenido de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e9309a-3ebb-4a9c-9d78-21c4e2bafc5b
ms.openlocfilehash: bdd7184d2b3a46f8ee59a052239dcd472db5e404
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651878"
---
# <a name="merging-dataset-contents"></a>Combinar contenido de DataSet

Se puede utilizar el método <xref:System.Data.DataSet.Merge%2A> para combinar el contenido de <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o matriz de <xref:System.Data.DataRow> en un `DataSet` existente. Hay varios factores y opciones que afectan a cómo se combinan los datos nuevos en un `DataSet` existente.

## <a name="primary-keys"></a>Claves principales

Si la tabla que recibe datos y esquema nuevos a partir de una fusión mediante combinación tiene una clave principal, las nuevas filas de los datos entrantes se hacen coincidir con las filas existentes que tienen los mismos valores de clave principal <xref:System.Data.DataRowVersion.Original> que los de los datos entrantes. Si las columnas del esquema entrante coinciden con las del esquema existente, se modificarán los datos de las filas existentes. Las columnas que no coincidan con el esquema existente se pasarán por alto o se agregarán en función del parámetro <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A>. Las nuevas filas con valores de clave principal que no coincidan con las filas existentes se agregarán a la tabla existente.

Si las filas entrantes o las existentes tienen un estado <xref:System.Data.DataRowState.Added>, se harán coincidir sus valores de clave principal mediante el valor de clave principal <xref:System.Data.DataRowVersion.Current> de la fila `Added`, ya que no existe ninguna versión de fila `Original`.

Si una tabla entrante y una tabla existente tienen una columna con el mismo nombre pero con distintos tipos de datos, se iniciará una excepción y se generará el evento <xref:System.Data.DataSet.MergeFailed> de `DataSet`. Si una tabla entrante y una tabla existente tienen claves definidas, pero las claves principales corresponden a columnas diferentes, se iniciará una excepción y se provocará el evento `MergeFailed` de `DataSet`.

Si la tabla que recibe nuevos datos de una combinación no tiene una clave principal, las nuevas filas de los datos entrantes no se pueden hacer coincidir con las filas existentes de la tabla y se agregarán a la tabla existente.

## <a name="table-names-and-namespaces"></a>Nombres de tabla y espacios de nombres

A los objetos <xref:System.Data.DataTable> se les puede asignarse también un valor de propiedad <xref:System.Data.DataTable.Namespace%2A>. Cuando se asignan los valores <xref:System.Data.DataTable.Namespace%2A>, <xref:System.Data.DataSet> puede contener varios objetos <xref:System.Data.DataTable> con el mismo valor <xref:System.Data.DataTable.TableName%2A>. Durante las operaciones de fusión mediante combinación, se utilizan tanto <xref:System.Data.DataTable.TableName%2A> como <xref:System.Data.DataTable.Namespace%2A> para identificar el destino de una fusión mediante combinación. Si no se ha asignado <xref:System.Data.DataTable.Namespace%2A> solo se utiliza <xref:System.Data.DataTable.TableName%2A> para identificar el destino de una fusión mediante combinación.

> [!NOTE]
> Este comportamiento ha cambiado en la versión 2.0 de .NET Framework. En la versión 1.1, se admitían los espacios de nombres pero eran pasados por alto durante las operaciones de fusión mediante combinación. Por ello, un <xref:System.Data.DataSet> que utiliza valores de propiedad <xref:System.Data.DataTable.Namespace%2A> tendrá diferentes comportamientos en función de la versión de .NET Framework que se ejecute. Por ejemplo, suponga que tiene dos `DataSets` que contienen `DataTables` con los mismos valores de propiedad <xref:System.Data.DataTable.TableName%2A> pero distintos valores de propiedad <xref:System.Data.DataTable.Namespace%2A>. En la versión 1.1 de .NET Framework, los nombres <xref:System.Data.DataTable.Namespace%2A> distintos serán pasados por alto cuando se combinen dos objetos <xref:System.Data.DataSet>. Sin embargo, a partir de la versión 2.0 de .NET Framework, la combinación produce dos nuevos `DataTables` para crearse en el <xref:System.Data.DataSet> de destino. El `DataTables` original no se verá afectado por la combinación.

## <a name="preservechanges"></a>PreserveChanges

Cuando se pasa una matriz de `DataSet`, `DataTable` o `DataRow` al método `Merge`, es posible incluir parámetros opcionales que especifiquen si se conservarán o no los cambios en el `DataSet` existente y cómo tratar los nuevos elementos de esquema de los datos entrantes. El primero de estos parámetros después de los datos entrantes es una marca booleana, <xref:System.Data.LoadOption.PreserveChanges>, que especifica si se conservarán o no los cambios en el `DataSet` existente. Si la marca `PreserveChanges` está establecida en `true`, los valores entrantes no sobrescriben los existentes en la versión de fila `Current` de la fila existente. Si la marca `PreserveChanges` está establecida en `false`, los valores entrantes sobrescriben los existentes en la versión de fila `Current` de la fila existente. Si la marca `PreserveChanges` no está especificado, de forma predeterminada se establece en `false`. Para obtener más información sobre las versiones de fila, vea [Estados de fila y versiones de fila](row-states-and-row-versions.md).

Cuando `PreserveChanges` es `true`, los datos de la fila existente se mantienen en la versión de fila <xref:System.Data.DataRowVersion.Current> de la fila existente, mientras que los datos de la versión de fila <xref:System.Data.DataRowVersion.Original> de la fila existente se sobrescriben con los datos de la versión de fila `Original` de la fila entrante. El <xref:System.Data.DataRow.RowState%2A> de la fila existente se establece en <xref:System.Data.DataRowState.Modified>. Se aplican las excepciones siguientes:

- Si la fila existente tiene un `RowState` de `Deleted`, `RowState` se mantiene en `Deleted` y no se establece en `Modified`. En este caso, los datos de la fila entrante se almacenarán en la versión de fila `Original` de la fila existente, sobrescribiendo la versión de fila `Original` de la fila existente (a menos que la fila entrante tenga un `RowState` de `Added`).

- Si la fila entrante tiene un `RowState` de `Added`, los datos de la versión de fila `Original` de la fila existente no se sobrescribirán con datos de la fila entrante, ya que ésta no tiene una versión de fila `Original`.

Cuando `PreserveChanges` es `false`, las versiones de fila `Current` y `Original` de la fila existente se sobrescriben con datos de la fila entrante y el `RowState` de la fila existente se establece como el `RowState` de la fila entrante. Se aplican las excepciones siguientes:

- Si la fila entrante tiene un `RowState` de `Unchanged` y la fila existente tiene un `RowState` de `Modified`, `Deleted` o `Added`, el `RowState` de la fila existente se establece en `Modified`.

- Si la fila entrante tiene un `RowState` de `Added` y la fila existente tiene un `RowState` de `Unchanged`, `Modified` o `Deleted`, el `RowState` de la fila existente se establece en `Modified`. Además, los datos de la versión de fila `Original` de la fila existente no se sobrescriben con datos de la fila entrante, ya que ésta no tiene una versión de fila `Original`.

## <a name="missingschemaaction"></a>MissingSchemaAction

Es posible utilizar el parámetro opcional <xref:System.Data.MissingSchemaAction> del método `Merge` para especificar cómo tratará `Merge` los elementos del esquema de los datos entrantes que no formen parte del `DataSet` existente.

En la siguiente tabla se describen las opciones de `MissingSchemaAction`.

|Opción MissingSchemaAction|Descripción|
|--------------------------------|-----------------|
|<xref:System.Data.MissingSchemaAction.Add>|Agrega al `DataSet` la nueva información de esquema y rellena las nuevas columnas con los valores entrantes. Este es el valor predeterminado.|
|<xref:System.Data.MissingSchemaAction.AddWithKey>|Agrega al `DataSet` la nueva información de esquema y de clave principal y rellena las nuevas columnas con los valores entrantes.|
|<xref:System.Data.MissingSchemaAction.Error>|Inicia una excepción si se encuentra información de esquema no coincidente.|
|<xref:System.Data.MissingSchemaAction.Ignore>|Pasa por alto la nueva información de esquema.|

## <a name="constraints"></a>Restricciones

Con el método `Merge` no se comprueban las restricciones hasta que se agregan todos los datos nuevos al `DataSet` existente. Una vez agregados los datos, se aplican restricciones en los valores actuales del `DataSet`. Hay que asegurarse de que el código controla las excepciones que puedan iniciarse debido a infracciones de las restricciones.

Tomemos como ejemplo un caso en el que una fila existente de un `DataSet` es una fila `Unchanged` con un valor de clave principal de 1. Durante una operación de combinación con una fila entrante `Modified` cuyo valor de clave principal `Original` es 2 y de clave principal `Current` es 1, la fila existente y la fila entrante no se consideran coincidentes porque los valores de clave principal `Original` son diferentes. Sin embargo, cuando se completa la combinación y se comprueban las restricciones, se iniciará una excepción porque los valores de clave principal `Current` infringen la restricción única de la columna de clave principal.

> [!NOTE]
> Cuando las filas están insertadas en una base de datos con columnas de incremento automático como puede ser una columna de identidad, el valor de columna de identidad devuelto por la inserción no coincide con el valor de `DataSet`, lo que da lugar a que las filas devueltas se agreguen en lugar de combinarse. Para obtener más información, vea [recuperar valores de identidad o Autonumérico](../retrieving-identity-or-autonumber-values.md).

En el ejemplo de código siguiente se combinan dos `DataSet` objetos con esquemas diferentes en uno `DataSet` con los esquemas combinados de los dos objetos de entrada `DataSet` .

[!code-csharp[DataWorks DataSet.Merge#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.Merge#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/VB/source.vb#1)]

En el siguiente ejemplo de código se toma un `DataSet` existente con actualizaciones y se pasan esas actualizaciones a un `DataAdapter` para que se procesen en el origen de datos. Los resultados se combinan entonces en el `DataSet` original. Después de rechazar los cambios que produjeron un error, se confirman los cambios combinados con `AcceptChanges`.

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#1)]

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#2)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#2)]

## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Estados y versiones de filas](row-states-and-row-versions.md)
- [Objetos DataAdapter y DataReader](../dataadapters-and-datareaders.md)
- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Recuperar valores autonuméricos y de identidad](../retrieving-identity-or-autonumber-values.md)
- [Información general de ADO.NET](../ado-net-overview.md)

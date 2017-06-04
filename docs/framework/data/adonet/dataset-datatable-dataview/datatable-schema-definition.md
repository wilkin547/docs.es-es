---
title: "Definici&#243;n de esquema de DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Definici&#243;n de esquema de DataTable
El esquema, o estructura, de una tabla se representa con columnas y restricciones.  El esquema de una <xref:System.Data.DataTable> se define mediante objetos <xref:System.Data.DataColumn>, <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>.  Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Las referencias a los nombres de columnas, relaciones y restricciones de una tabla hacen distinción entre mayúsculas y minúsculas.  En una tabla puede haber dos o más columnas, relaciones y restricciones con el mismo nombre, pero con distinción entre mayúsculas y minúsculas.  Por ejemplo, se puede tener **Col1** y **col1**.  En este caso, una referencia al nombre de una de las columnas tiene que coincidir exactamente con las mayúsculas y minúsculas del nombre de la columna, de lo contrario se inicia una excepción.  Por ejemplo, si la tabla **myTable** contiene las columnas **Col1** y **col1**, la referencia al nombre de **Col1** sería **myTable.Columns\["Col1"\]** y al de **col1** sería **myTable.Columns\["col1"\]**.  Si se intentara hacer referencia a cualquiera de las columnas mediante **myTable.Columns\["COL1"\]** se generaría una excepción.  
  
 La regla de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una columna, relación o restricción con un nombre concreto.  Es decir, si no hay ningún otro objeto de columna, relación o restricción en la tabla que coincida con el nombre de ese objeto de columna, relación o restricción concreto, se puede hacer referencia al nombre del objeto utilizando cualquier mayúscula o minúscula y no se generará una excepción.  Por ejemplo, si la tabla sólo tiene **Col1**, se puede hacer referencia al nombre usando **my.Columns\["COL1"\]**.  
  
> [!NOTE]
>  La propiedad <xref:System.Data.DataTable.CaseSensitive%2A> de la **DataTable** no afecta a este comportamiento.  La propiedad **CaseSensitive** se aplica a los datos de una tabla y afecta al ordenamiento, la búsqueda, el filtrado, la aplicación de restricciones, etcétera, pero no afecta a referencias a columnas, relaciones ni restricciones.  
  
## En esta sección  
 [Agregar columnas a la DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Describe cómo se definen las columnas de una tabla con objetos **DataColumn**.  
  
 [Crear columnas de expresión](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Explica cómo se puede utilizar la propiedad **Expression** de una columna para calcular valores basándose en los valores de otras columnas de la fila.  
  
 [Crear columnas AutoIncrement](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Describe cómo se puede establecer una columna para que incremente automáticamente los valores numéricos y, así, se garantice un valor de columna exclusivo por fila.  
  
 [Definir claves principales](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Describe cómo se especifica la clave principal de una tabla a partir de uno o varios objetos **DataColumn**.  
  
 [Restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Describe cómo se define una clave externa y restricciones UNIQUE para las columnas de una tabla.  
  
## Vea también  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)
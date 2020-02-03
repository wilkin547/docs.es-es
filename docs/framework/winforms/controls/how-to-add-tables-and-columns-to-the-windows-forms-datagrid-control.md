---
title: Agregar tablas y columnas al control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747213"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

Puede mostrar los datos en el control Windows Forms <xref:System.Windows.Forms.DataGrid> en tablas y columnas mediante la creación de objetos **DataGridTableStyle** y su adición al objeto **GridTableStylesCollection** , al que se tiene acceso a través de la propiedad **TableStyles** del control <xref:System.Windows.Forms.DataGrid>. Cada estilo de tabla muestra el contenido de la tabla de datos especificada en la propiedad **MappingName** del objeto **DataGridTableStyle** . De forma predeterminada, un estilo de tabla sin estilos de columna especificado mostrará todas las columnas de esa tabla de datos. Puede restringir Qué columnas de la tabla aparecen agregando objetos **DataGridColumnStyle** al objeto **GridColumnStylesCollection** , al que se tiene acceso a través de la propiedad **GridColumnStyles** de cada objeto **DataGridTableStyle** .

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Para agregar una tabla y una columna a un control DataGrid mediante programación

1. Para mostrar los datos en la tabla, primero debe enlazar el control <xref:System.Windows.Forms.DataGrid> a un conjunto de datos. Para obtener más información, vea [Cómo: enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

    > [!CAUTION]
    > Al especificar estilos de columna mediante programación, cree siempre objetos **DataGridColumnStyle** y agréguelos al objeto **GridColumnStylesCollection** antes de agregar objetos **DataGridTableStyle** al objeto **GridTableStylesCollection** . Al agregar un objeto **DataGridTableStyle** vacío a la colección, se generan automáticamente los objetos **DataGridColumnStyle** . Por consiguiente, se producirá una excepción si intenta agregar nuevos objetos **DataGridColumnStyle** con valores **MappingName** duplicados al objeto **GridColumnStylesCollection** .

2. Declare un nuevo estilo de tabla y establezca el nombre de la asignación.

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. Declare un nuevo estilo de columna y establezca el nombre de la asignación y otras propiedades.

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. Llame al método **Add** del objeto **GridColumnStylesCollection** para agregar la columna al estilo de tabla.

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. Llame al método **Add** del objeto **GridTableStylesCollection** para agregar el estilo de tabla a la cuadrícula de datos.

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>Consulte también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)

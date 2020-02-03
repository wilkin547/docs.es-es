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
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="369a6-102">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="369a6-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="369a6-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="369a6-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="369a6-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="369a6-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="369a6-105">Puede mostrar los datos en el control Windows Forms <xref:System.Windows.Forms.DataGrid> en tablas y columnas mediante la creación de objetos **DataGridTableStyle** y su adición al objeto **GridTableStylesCollection** , al que se tiene acceso a través de la propiedad **TableStyles** del control <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="369a6-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="369a6-106">Cada estilo de tabla muestra el contenido de la tabla de datos especificada en la propiedad **MappingName** del objeto **DataGridTableStyle** .</span><span class="sxs-lookup"><span data-stu-id="369a6-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="369a6-107">De forma predeterminada, un estilo de tabla sin estilos de columna especificado mostrará todas las columnas de esa tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="369a6-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="369a6-108">Puede restringir Qué columnas de la tabla aparecen agregando objetos **DataGridColumnStyle** al objeto **GridColumnStylesCollection** , al que se tiene acceso a través de la propiedad **GridColumnStyles** de cada objeto **DataGridTableStyle** .</span><span class="sxs-lookup"><span data-stu-id="369a6-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="369a6-109">Para agregar una tabla y una columna a un control DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="369a6-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="369a6-110">Para mostrar los datos en la tabla, primero debe enlazar el control <xref:System.Windows.Forms.DataGrid> a un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="369a6-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="369a6-111">Para obtener más información, vea [Cómo: enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="369a6-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="369a6-112">Al especificar estilos de columna mediante programación, cree siempre objetos **DataGridColumnStyle** y agréguelos al objeto **GridColumnStylesCollection** antes de agregar objetos **DataGridTableStyle** al objeto **GridTableStylesCollection** .</span><span class="sxs-lookup"><span data-stu-id="369a6-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="369a6-113">Al agregar un objeto **DataGridTableStyle** vacío a la colección, se generan automáticamente los objetos **DataGridColumnStyle** .</span><span class="sxs-lookup"><span data-stu-id="369a6-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="369a6-114">Por consiguiente, se producirá una excepción si intenta agregar nuevos objetos **DataGridColumnStyle** con valores **MappingName** duplicados al objeto **GridColumnStylesCollection** .</span><span class="sxs-lookup"><span data-stu-id="369a6-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="369a6-115">Declare un nuevo estilo de tabla y establezca el nombre de la asignación.</span><span class="sxs-lookup"><span data-stu-id="369a6-115">Declare a new table style and set its mapping name.</span></span>

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

3. <span data-ttu-id="369a6-116">Declare un nuevo estilo de columna y establezca el nombre de la asignación y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="369a6-116">Declare a new column style and set its mapping name and other properties.</span></span>

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

4. <span data-ttu-id="369a6-117">Llame al método **Add** del objeto **GridColumnStylesCollection** para agregar la columna al estilo de tabla.</span><span class="sxs-lookup"><span data-stu-id="369a6-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="369a6-118">Llame al método **Add** del objeto **GridTableStylesCollection** para agregar el estilo de tabla a la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="369a6-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="369a6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="369a6-119">See also</span></span>

- [<span data-ttu-id="369a6-120">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="369a6-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="369a6-121">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="369a6-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)

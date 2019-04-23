---
title: Procedimiento para agregar tablas y columnas al control DataGrid de Windows Forms
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
ms.openlocfilehash: cc364f3609f8041378b0b03b8e1bc8f312fade18
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319916"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="41b36-102">Procedimiento para agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41b36-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="41b36-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="41b36-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="41b36-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="41b36-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="41b36-105">Puede mostrar datos en los formularios de Windows <xref:System.Windows.Forms.DataGrid> control en las tablas y columnas mediante la creación de **DataGridTableStyle** objetos y agregarlos a la **GridTableStylesCollection** objeto, que es tiene acceso a través del <xref:System.Windows.Forms.DataGrid> del control **TableStyles** propiedad.</span><span class="sxs-lookup"><span data-stu-id="41b36-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="41b36-106">Cada tabla muestra el contenido de la tabla de datos se haya especificado en el **DataGridTableStyle** del objeto **MappingName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="41b36-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="41b36-107">De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas dentro de esa tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="41b36-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="41b36-108">Puede restringir qué columnas de la tabla aparecen agregando **DataGridColumnStyle** objetos a la **GridColumnStylesCollection** objeto, que se accede mediante el  **GridColumnStyles** propiedad de cada uno **DataGridTableStyle** objeto.</span><span class="sxs-lookup"><span data-stu-id="41b36-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="41b36-109">Para agregar una tabla y columna a un control DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="41b36-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="41b36-110">Para mostrar los datos en la tabla, se debe enlazar el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="41b36-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="41b36-111">Para obtener más información, vea [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="41b36-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="41b36-112">Cuando especifique estilos de columna mediante programación, cree siempre **DataGridColumnStyle** objetos y agregarlos a la **GridColumnStylesCollection** objeto antes de agregar  **DataGridTableStyle** objetos a la **GridTableStylesCollection** objeto.</span><span class="sxs-lookup"><span data-stu-id="41b36-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="41b36-113">Cuando se agrega un valor vacío **DataGridTableStyle** objeto a la colección, **DataGridColumnStyle** los objetos se generan automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="41b36-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="41b36-114">Por lo tanto, se producirá una excepción si intenta agregar nuevo **DataGridColumnStyle** objetos con duplicado **MappingName** valores para el **GridColumnStylesCollection**objeto.</span><span class="sxs-lookup"><span data-stu-id="41b36-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2. <span data-ttu-id="41b36-115">Declare un nuevo estilo de tabla y establezca su nombre de asignación.</span><span class="sxs-lookup"><span data-stu-id="41b36-115">Declare a new table style and set its mapping name.</span></span>  
  
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
  
3. <span data-ttu-id="41b36-116">Declare un nuevo estilo de columna y establezca su nombre de asignación y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="41b36-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
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
  
4. <span data-ttu-id="41b36-117">Llame a la **agregar** método de la **GridColumnStylesCollection** objeto va a agregar la columna para el estilo de tabla</span><span class="sxs-lookup"><span data-stu-id="41b36-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5. <span data-ttu-id="41b36-118">Llame a la **agregar** método de la **GridTableStylesCollection** objeto va a agregar el estilo de tabla a la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="41b36-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41b36-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="41b36-119">See also</span></span>

- [<span data-ttu-id="41b36-120">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="41b36-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="41b36-121">Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41b36-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)

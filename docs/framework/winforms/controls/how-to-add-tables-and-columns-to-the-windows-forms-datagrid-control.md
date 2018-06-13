---
title: 'Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms'
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
ms.openlocfilehash: fc8161ea29da92f5dcc2e76f956f3fecd6140acc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527724"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="3b28f-102">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b28f-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="3b28f-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="3b28f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3b28f-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="3b28f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3b28f-105">Puede mostrar datos en formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control en tablas y columnas mediante la creación de **DataGridTableStyle** objetos y agregándolos a la **GridTableStylesCollection** objeto, que es acceso a través de la <xref:System.Windows.Forms.DataGrid> del control **TableStyles** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b28f-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="3b28f-106">Cada estilo de tabla muestra el contenido de la tabla de datos se haya especificado en el **DataGridTableStyle** del objeto **MappingName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b28f-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="3b28f-107">De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas de esa tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="3b28f-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="3b28f-108">Puede restringir las columnas de la tabla que aparecen agregando **DataGridColumnStyle** objetos a la **GridColumnStylesCollection** objeto, que se obtiene acceso a través de la  **GridColumnStyles** propiedad de cada **DataGridTableStyle** objeto.</span><span class="sxs-lookup"><span data-stu-id="3b28f-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="3b28f-109">Para agregar una tabla y una columna a un control DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="3b28f-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="3b28f-110">Para mostrar los datos en la tabla, debe enlazar primero el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3b28f-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="3b28f-111">Para obtener más información, consulte [Cómo: enlazar el DataGrid Control de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="3b28f-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="3b28f-112">Cuando especifique estilos de columna mediante programación, cree siempre **DataGridColumnStyle** objetos y agréguelos a la **GridColumnStylesCollection** objeto antes de agregar  **DataGridTableStyle** objetos a la **GridTableStylesCollection** objeto.</span><span class="sxs-lookup"><span data-stu-id="3b28f-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="3b28f-113">Cuando se agrega vacío **DataGridTableStyle** objeto a la colección, **DataGridColumnStyle** objetos se generan automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="3b28f-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="3b28f-114">Por lo tanto, se producirá una excepción si intenta agregar nuevos **DataGridColumnStyle** objetos con duplicado **MappingName** valores a la **GridColumnStylesCollection**objeto.</span><span class="sxs-lookup"><span data-stu-id="3b28f-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="3b28f-115">Declare un nuevo estilo de tabla y establezca su nombre de asignación.</span><span class="sxs-lookup"><span data-stu-id="3b28f-115">Declare a new table style and set its mapping name.</span></span>  
  
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
  
3.  <span data-ttu-id="3b28f-116">Declare un nuevo estilo de columna y establezca su nombre de la asignación y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="3b28f-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
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
  
4.  <span data-ttu-id="3b28f-117">Llame a la **agregar** método de la **GridColumnStylesCollection** objeto que se va a agregar la columna en el estilo de tabla</span><span class="sxs-lookup"><span data-stu-id="3b28f-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="3b28f-118">Llame a la **agregar** método de la **GridTableStylesCollection** va a agregar el estilo de tabla a la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="3b28f-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3b28f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b28f-119">See Also</span></span>  
 [<span data-ttu-id="3b28f-120">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="3b28f-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="3b28f-121">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b28f-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)

---
title: Procedimiento para eliminar u ocultar columnas del control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: d3f1f013cbb5e41c997014f556602b01bab62914
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757396"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="7fe06-102">Procedimiento para eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fe06-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="7fe06-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="7fe06-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="7fe06-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="7fe06-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="7fe06-105">Mediante programación puede eliminar u ocultar columnas en los formularios de Windows <xref:System.Windows.Forms.DataGrid> control mediante el uso de las propiedades y métodos de la <xref:System.Windows.Forms.GridColumnStylesCollection> y <xref:System.Windows.Forms.DataGridColumnStyle> objetos (que son miembros de la <xref:System.Windows.Forms.DataGridTableStyle> clase).</span><span class="sxs-lookup"><span data-stu-id="7fe06-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="7fe06-106">Las columnas eliminadas u ocultas siguen existan en el origen de datos se enlaza a la cuadrícula y todavía pueden tener acceso mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7fe06-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="7fe06-107">Simplemente ya no son visibles en la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="7fe06-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe06-108">Si la aplicación no tiene acceso a determinadas columnas de datos y no desea que se muestra en la cuadrícula de datos, probablemente no es necesario incluir en el origen de datos en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="7fe06-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="7fe06-109">Para eliminar una columna de la cuadrícula de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="7fe06-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="7fe06-110">En el área de declaraciones del formulario, declare una nueva instancia de la <xref:System.Windows.Forms.DataGridTableStyle> clase.</span><span class="sxs-lookup"><span data-stu-id="7fe06-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="7fe06-111">Establecer el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> propiedad a la tabla de origen de datos que desea aplicar el estilo.</span><span class="sxs-lookup"><span data-stu-id="7fe06-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="7fe06-112">En el ejemplo siguiente se usa el <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> propiedad, que se supone que ya se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="7fe06-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="7fe06-113">Agregue el nuevo <xref:System.Windows.Forms.DataGridTableStyle> objeto a la colección de estilos de tabla del control datagrid.</span><span class="sxs-lookup"><span data-stu-id="7fe06-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="7fe06-114">Llame a la <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.DataGrid>del <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> colección, especificando el índice de columna de la columna que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="7fe06-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="7fe06-115">Para ocultar una columna en la cuadrícula de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="7fe06-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="7fe06-116">En el área de declaraciones del formulario, declare una nueva instancia de la <xref:System.Windows.Forms.DataGridTableStyle> clase.</span><span class="sxs-lookup"><span data-stu-id="7fe06-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="7fe06-117">Establecer el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle> a la tabla de origen de datos que desea aplicar el estilo.</span><span class="sxs-lookup"><span data-stu-id="7fe06-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="7fe06-118">El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> propiedad, que se supone que ya se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="7fe06-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="7fe06-119">Agregue el nuevo <xref:System.Windows.Forms.DataGridTableStyle> objeto a la colección de estilos de tabla del control datagrid.</span><span class="sxs-lookup"><span data-stu-id="7fe06-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="7fe06-120">Ocultar la columna estableciendo su `Width` propiedad en 0, especificando el índice de columna de la columna que desea ocultar.</span><span class="sxs-lookup"><span data-stu-id="7fe06-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7fe06-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fe06-121">See also</span></span>

- [<span data-ttu-id="7fe06-122">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fe06-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="7fe06-123">Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fe06-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)

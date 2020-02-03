---
title: Validar la entrada con el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728300"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="e30c8-102">Cómo: Validar los datos introducidos con el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e30c8-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="e30c8-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="e30c8-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e30c8-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="e30c8-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="e30c8-105">Hay dos tipos de validación de entrada disponibles para el control Windows Forms <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="e30c8-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="e30c8-106">Si el usuario intenta especificar un valor que es de un tipo de datos inaceptable para la celda, por ejemplo una cadena en un entero, el nuevo valor no válido se reemplaza por el valor anterior.</span><span class="sxs-lookup"><span data-stu-id="e30c8-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="e30c8-107">Este tipo de validación de entrada se realiza automáticamente y no se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="e30c8-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="e30c8-108">El otro tipo de validación de entrada se puede usar para rechazar cualquier dato inaceptable; por ejemplo, un valor 0 en un campo que debe ser mayor o igual que 1, o una cadena no adecuada.</span><span class="sxs-lookup"><span data-stu-id="e30c8-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="e30c8-109">Esto se hace en el conjunto de DataSet escribiendo un controlador de eventos para el evento <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging>.</span><span class="sxs-lookup"><span data-stu-id="e30c8-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="e30c8-110">En el ejemplo siguiente se usa el evento <xref:System.Data.DataTable.ColumnChanging> porque no se permite el valor inaceptable para la columna "Product" en particular.</span><span class="sxs-lookup"><span data-stu-id="e30c8-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="e30c8-111">Puede usar el evento <xref:System.Data.DataTable.RowChanging> para comprobar que el valor de una columna "fecha de finalización" es posterior a la columna "fecha de inicio" de la misma fila.</span><span class="sxs-lookup"><span data-stu-id="e30c8-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="e30c8-112">Para validar la entrada del usuario</span><span class="sxs-lookup"><span data-stu-id="e30c8-112">To validate user input</span></span>

1. <span data-ttu-id="e30c8-113">Escriba código para controlar el evento de <xref:System.Data.DataTable.ColumnChanging> de la tabla adecuada.</span><span class="sxs-lookup"><span data-stu-id="e30c8-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="e30c8-114">Cuando se detecten entradas inadecuadas, llame al método <xref:System.Data.DataRow.SetColumnError%2A> del objeto <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="e30c8-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. <span data-ttu-id="e30c8-115">Conecte el controlador de eventos al evento.</span><span class="sxs-lookup"><span data-stu-id="e30c8-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="e30c8-116">Coloque el código siguiente en el evento <xref:System.Windows.Forms.Form.Load> del formulario o en su constructor.</span><span class="sxs-lookup"><span data-stu-id="e30c8-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a><span data-ttu-id="e30c8-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e30c8-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="e30c8-118">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="e30c8-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)

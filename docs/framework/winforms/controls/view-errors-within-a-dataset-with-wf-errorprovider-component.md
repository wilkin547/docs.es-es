---
title: Procedimiento Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 48f333fbae816748813b370bccc559cea2714fa5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694053"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="70978-102">Procedimiento Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70978-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="70978-103">Puede usar los formularios de Windows <xref:System.Windows.Forms.ErrorProvider> componente para ver los errores de la columna dentro de un conjunto de datos o de otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="70978-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="70978-104">Para un <xref:System.Windows.Forms.ErrorProvider> componente para mostrar los errores de datos en un formulario, no tiene que estar directamente asociado a un control.</span><span class="sxs-lookup"><span data-stu-id="70978-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="70978-105">Una vez que está enlazado a un origen de datos, puede mostrar un icono de error junto a cualquier control que está enlazado al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="70978-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70978-106">Si cambia el proveedor de errores <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> y <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> propiedades en tiempo de ejecución, debe usar el <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> método para evitar conflictos.</span><span class="sxs-lookup"><span data-stu-id="70978-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="70978-107">Para mostrar los errores de datos</span><span class="sxs-lookup"><span data-stu-id="70978-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="70978-108">Enlazar el componente a una columna específica dentro de una tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="70978-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  <span data-ttu-id="70978-109">Establecer el <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad al formulario.</span><span class="sxs-lookup"><span data-stu-id="70978-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="70978-110">Establezca la posición del registro actual en una fila que contiene un error de la columna.</span><span class="sxs-lookup"><span data-stu-id="70978-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="70978-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="70978-111">See also</span></span>
- [<span data-ttu-id="70978-112">Información general del componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="70978-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="70978-113">Cómo: Mostrar iconos de Error de validación de formularios con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70978-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)

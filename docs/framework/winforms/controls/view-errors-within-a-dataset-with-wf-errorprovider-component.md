---
title: Ver errores dentro de un conjunto de DataSet mediante el componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745452"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="a9ef7-102">Cómo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9ef7-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="a9ef7-103">Puede utilizar el componente Windows Forms <xref:System.Windows.Forms.ErrorProvider> para ver los errores de columna dentro de un conjunto de datos o de otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="a9ef7-104">Para que un componente de <xref:System.Windows.Forms.ErrorProvider> muestre errores de datos en un formulario, no tiene que estar asociado directamente a un control.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="a9ef7-105">Una vez enlazado a un origen de datos, puede mostrar un icono de error junto a cualquier control que esté enlazado al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9ef7-106">Si cambia las propiedades <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> y <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> del proveedor de errores en tiempo de ejecución, debe utilizar el método <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> para evitar conflictos.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="a9ef7-107">Para mostrar errores de datos</span><span class="sxs-lookup"><span data-stu-id="a9ef7-107">To display data errors</span></span>  
  
1. <span data-ttu-id="a9ef7-108">Enlazar el componente a una columna específica dentro de una tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-108">Bind the component to a specific column within a data table.</span></span>  
  
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
  
2. <span data-ttu-id="a9ef7-109">Establezca la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="a9ef7-110">Establece la posición del registro actual en una fila que contiene un error de columna.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a9ef7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9ef7-111">See also</span></span>

- [<span data-ttu-id="a9ef7-112">Información general del componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a9ef7-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="a9ef7-113">Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9ef7-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)

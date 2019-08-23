---
title: Procedimiento para ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 3dbd2ccca607869a6f28bc5b3bd1c9f0769db9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950080"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Procedimiento para ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms
Puede utilizar el componente Windows Forms <xref:System.Windows.Forms.ErrorProvider> para ver los errores de columna dentro de un conjunto de datos o de otro origen de datos. Para que <xref:System.Windows.Forms.ErrorProvider> un componente muestre errores de datos en un formulario, no tiene que estar asociado directamente a un control. Una vez enlazado a un origen de datos, puede mostrar un icono de error junto a cualquier control que esté enlazado al mismo origen de datos.  
  
> [!NOTE]
> Si cambia las propiedades y <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> del proveedor de errores en tiempo de ejecución, debe utilizar el <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> método para evitar conflictos.  
  
### <a name="to-display-data-errors"></a>Para mostrar errores de datos  
  
1. Enlazar el componente a una columna específica dentro de una tabla de datos.  
  
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
  
2. Establezca la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad en el formulario.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. Establece la posición del registro actual en una fila que contiene un error de columna.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>Vea también

- [Información general del componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)

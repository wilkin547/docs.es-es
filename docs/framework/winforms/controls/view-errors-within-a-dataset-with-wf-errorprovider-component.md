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
ms.openlocfilehash: 15fbf4a3cebef1485f0c54ace36ab88f3d4289e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310452"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Procedimiento para ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms
Puede usar los formularios de Windows <xref:System.Windows.Forms.ErrorProvider> componente para ver los errores de la columna dentro de un conjunto de datos o de otro origen de datos. Para un <xref:System.Windows.Forms.ErrorProvider> componente para mostrar los errores de datos en un formulario, no tiene que estar directamente asociado a un control. Una vez que está enlazado a un origen de datos, puede mostrar un icono de error junto a cualquier control que está enlazado al mismo origen de datos.  
  
> [!NOTE]
>  Si cambia el proveedor de errores <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> y <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> propiedades en tiempo de ejecución, debe usar el <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> método para evitar conflictos.  
  
### <a name="to-display-data-errors"></a>Para mostrar los errores de datos  
  
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
  
2. Establecer el <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad al formulario.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. Establezca la posición del registro actual en una fila que contiene un error de la columna.  
  
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
- [Cómo: Mostrar iconos de Error de validación de formularios con el componente ErrorProvider de formularios Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)

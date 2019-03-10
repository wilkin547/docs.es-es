---
title: Procedimiento Ordenar y filtrar datos ADO.NET con el Windows Forms BindingSource (componente)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 65be2367091144945e9540c848e6131deac9d725
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703108"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Filtrar Ordenar y filtrar datos ADO.NET con el Windows Forms BindingSource (componente)
Puede exponer la ordenación y filtrado de capacidad de <xref:System.Windows.Forms.BindingSource> controlar a través de la <xref:System.Windows.Forms.BindingSource.Sort%2A> y <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedades. Puede aplicar la ordenación simple si el origen de datos subyacente es un <xref:System.ComponentModel.IBindingList>, y puede aplicar el filtrado y ordenación cuando el origen de datos es avanzada un <xref:System.ComponentModel.IBindingListView>. El <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad requiere estándar [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] sintaxis: una cadena que representa el nombre de una columna de datos del origen de datos seguida `ASC` o `DESC` para indicar si la lista debe ordenarse en orden ascendente o descendente. Puede establecer la ordenación avanzada o varias columnas de ordenación separando cada columna con un separador de coma. El <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad toma una expresión de cadena.  
  
> [!NOTE]
>  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Para filtrar los datos con el componente BindingSource  
  
-   Establecer el <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad a la expresión que desea.  
  
     En el ejemplo de código siguiente, la expresión es un nombre de columna seguido de valor que desee para la columna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Para ordenar los datos con el componente BindingSource  
  
1.  Establecer el <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad en el nombre de columna que desee seguido `ASC` o `DESC` para indicar el orden ascendente o descendente.  
  
2.  Separe varias columnas con una coma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código carga los datos de la tabla Customers de la base de datos de ejemplo Northwind en un <xref:System.Windows.Forms.DataGridView> controlar y filtra y ordena los datos mostrados.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este ejemplo, pegue el código en un formulario que contenga un <xref:System.Windows.Forms.BindingSource> denominado `BindingSource1` y un <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`. Controlar la <xref:System.Windows.Forms.Form.Load> eventos para el formulario y llame a `InitializeSortedFilteredBindingSource` en el método de controlador de eventos de carga.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Cómo: Instalar bases de datos de ejemplo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](bindingsource-component.md)

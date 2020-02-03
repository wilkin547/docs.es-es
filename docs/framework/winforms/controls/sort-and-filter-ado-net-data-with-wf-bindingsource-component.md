---
title: Ordenar y filtrar datos ADO.NET con el componente BindingSource
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
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742978"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms
Puede exponer la funcionalidad de ordenación y filtrado de <xref:System.Windows.Forms.BindingSource> control a través de las propiedades <xref:System.Windows.Forms.BindingSource.Sort%2A> y <xref:System.Windows.Forms.BindingSource.Filter%2A>. Puede aplicar una ordenación simple cuando el origen de datos subyacente es un <xref:System.ComponentModel.IBindingList>y puede aplicar filtrado y ordenación avanzada cuando el origen de datos es un <xref:System.ComponentModel.IBindingListView>. La propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> requiere la sintaxis estándar de ADO.NET: una cadena que representa el nombre de una columna de datos en el origen de datos seguida de `ASC` o `DESC` para indicar si la lista debe ordenarse en orden ascendente o descendente. Puede establecer la ordenación avanzada o la ordenación de varias columnas separando cada columna con un separador de coma. La propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> toma una expresión de cadena.  
  
> [!NOTE]
> Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Para filtrar datos con BindingSource  
  
- Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> en la expresión que desee.  
  
     En el ejemplo de código siguiente, la expresión es un nombre de columna seguido por el valor que desea para la columna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Para ordenar los datos con BindingSource  
  
1. Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> en el nombre de columna que desee seguido de `ASC` o `DESC` para indicar el orden ascendente o descendente.  
  
2. Separe varias columnas con una coma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se cargan datos de la tabla Customers de la base de datos de ejemplo Northwind en un control <xref:System.Windows.Forms.DataGridView>, y se filtran y se ordenan los datos mostrados.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este ejemplo, pegue el código en un formulario que contenga una <xref:System.Windows.Forms.BindingSource> denominada `BindingSource1` y una <xref:System.Windows.Forms.DataGridView> denominada `dataGridView1`. Controle el evento <xref:System.Windows.Forms.Form.Load> del formulario y llame a `InitializeSortedFilteredBindingSource` en el método de control de eventos Load.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Cómo: Instalar bases de datos de ejemplo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](bindingsource-component.md)

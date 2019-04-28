---
title: Procedimiento para desplazarse por los datos en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2ba33f9ecb3a12a62c41af17d3f9ad6f6e3f8a5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801717"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Procedimiento para desplazarse por los datos en formularios Windows Forms
En una aplicación de Windows, la manera más fácil de navegar por los registros de un origen de datos es enlazar un <xref:System.Windows.Forms.BindingSource> componente para el origen de datos y, a continuación, enlazar controles a la <xref:System.Windows.Forms.BindingSource>. A continuación, puede usar el método de exploración integrada en el <xref:System.Windows.Forms.BindingSource> tales un <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> y <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Uso de estos métodos se ajustará el <xref:System.Windows.Forms.BindingSource.Position%2A> y <xref:System.Windows.Forms.BindingSource.Current%2A> propiedades de la <xref:System.Windows.Forms.BindingSource> adecuadamente. También puede encontrar un elemento y establecerlo como el elemento actual estableciendo el <xref:System.Windows.Forms.BindingSource.Position%2A> propiedad.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Para incrementar la posición de un origen de datos  
  
1. Establecer el <xref:System.Windows.Forms.BindingSource.Position%2A> propiedad de la <xref:System.Windows.Forms.BindingSource> para los datos enlazados a la posición del registro para ir a. El ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Forms.BindingSource.MoveNext%2A> método de la <xref:System.Windows.Forms.BindingSource> para incrementar la <xref:System.Windows.Forms.BindingSource.Position%2A> propiedad cuando la `nextButton` se hace clic en. El <xref:System.Windows.Forms.BindingSource> está asociado el `Customers` tabla de un conjunto de datos `Northwind`.  
  
    > [!NOTE]
    >  Establecer el <xref:System.Windows.Forms.BindingSource.Position%2A> propiedad con un valor más allá del primer o último registro no se produce un error, como el [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no le permitirá establecer la posición en un valor fuera de los límites de la lista. Si es importante en la aplicación saber si ha sobrepasado el primer o último registro, incluya la lógica para comprobar si se superó el número de elementos de datos.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Para comprobar si han pasado el final o el principio  
  
1. Cree un controlador para el evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. En el controlador, puede probar si el valor de posición propuesta ha superado el número de elementos de datos reales.  
  
     El ejemplo siguiente muestra cómo puede probar si se ha alcanzado el último elemento de datos. En el ejemplo, si se encuentra en el último elemento, el **siguiente** botón en el formulario está deshabilitado.  
  
    > [!NOTE]
    >  Tenga en cuenta que, si cambia la lista que está explorando en código, debe volver a habilitar la **siguiente** button, para que los usuarios puedan examinar toda la longitud de la nueva lista. Además, tenga en cuenta que el anterior <xref:System.Windows.Forms.BindingSource.PositionChanged> evento específica para la <xref:System.Windows.Forms.BindingSource> que está trabajando debe estar asociado a su método de control de eventos. El siguiente es un ejemplo de un método para controlar la <xref:System.Windows.Forms.BindingSource.PositionChanged> eventos:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Para encontrar un elemento y establecerlo como el elemento actual  
  
1. Buscar el registro que desea establecer como el elemento actual. Puede hacerlo mediante el <xref:System.Windows.Forms.BindingSource.Find%2A> método de la <xref:System.Windows.Forms.BindingSource>, si el origen de datos implementa <xref:System.ComponentModel.IBindingList>. Algunos ejemplos de datos de orígenes que implementan <xref:System.ComponentModel.IBindingList> son <xref:System.ComponentModel.BindingList%601> y <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Orígenes de datos compatibles con Windows Forms](data-sources-supported-by-windows-forms.md)
- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)

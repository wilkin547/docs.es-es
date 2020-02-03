---
title: 'Cómo: navegar por los datos'
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
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739399"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Cómo: Desplazarse por datos en Windows Forms
En una aplicación de Windows, la forma más sencilla de desplazarse por los registros de un origen de datos es enlazar un <xref:System.Windows.Forms.BindingSource> componente al origen de datos y, a continuación, enlazar los controles al <xref:System.Windows.Forms.BindingSource>. Después, puede usar el método de navegación integrado en el <xref:System.Windows.Forms.BindingSource> como <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> y <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. El uso de estos métodos ajustará las propiedades <xref:System.Windows.Forms.BindingSource.Position%2A> y <xref:System.Windows.Forms.BindingSource.Current%2A> de la <xref:System.Windows.Forms.BindingSource> de forma adecuada. También puede buscar un elemento y establecerlo como el elemento actual estableciendo la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A>.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Para incrementar la posición en un origen de datos  
  
1. Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> del <xref:System.Windows.Forms.BindingSource> de los datos enlazados en la posición del registro a la que va a ir. En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Forms.BindingSource.MoveNext%2A> del <xref:System.Windows.Forms.BindingSource> para incrementar la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> cuando se hace clic en el `nextButton`. El <xref:System.Windows.Forms.BindingSource> está asociado a la tabla de `Customers` de un conjunto de `Northwind`.  
  
    > [!NOTE]
    > Al establecer la propiedad <xref:System.Windows.Forms.BindingSource.Position%2A> en un valor más allá del primer o último registro no se produce un error, ya que el .NET Framework no le permitirá establecer la posición en un valor fuera de los límites de la lista. Si es importante en la aplicación saber si ha pasado el primer o el último registro, incluya lógica para comprobar si se superará el recuento de elementos de datos.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Para comprobar si ha pasado el final o el principio  
  
1. Cree un controlador para el evento <xref:System.Windows.Forms.BindingSource.PositionChanged>. En el controlador, puede comprobar si el valor de la posición propuesta ha superado el número real de elementos de datos.  
  
     En el ejemplo siguiente se muestra cómo se puede comprobar si se ha alcanzado el último elemento de datos. En el ejemplo, si se encuentra en el último elemento, el botón **siguiente** del formulario está deshabilitado.  
  
    > [!NOTE]
    > Tenga en cuenta que, si cambia la lista que está navegando por el código, debe volver a habilitar el botón **siguiente** para que los usuarios puedan examinar la longitud completa de la nueva lista. Además, tenga en cuenta que el evento de <xref:System.Windows.Forms.BindingSource.PositionChanged> anterior para el <xref:System.Windows.Forms.BindingSource> específico con el que está trabajando debe estar asociado a su método de control de eventos. El siguiente es un ejemplo de un método para controlar el evento <xref:System.Windows.Forms.BindingSource.PositionChanged>:  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Para buscar un elemento y establecerlo como elemento actual  
  
1. Busque el registro que desea establecer como elemento actual. Puede hacerlo mediante el método <xref:System.Windows.Forms.BindingSource.Find%2A> del <xref:System.Windows.Forms.BindingSource>, si el origen de datos implementa <xref:System.ComponentModel.IBindingList>. Algunos ejemplos de orígenes de datos que implementan <xref:System.ComponentModel.IBindingList> son <xref:System.ComponentModel.BindingList%601> y <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Orígenes de datos compatibles con Windows Forms](data-sources-supported-by-windows-forms.md)
- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)

---
title: 'Cómo: Mostrar el contenido de ListView mediante un control GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 103a439b9cee959d0077e5a759364eb9b943905d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554056"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Cómo: Mostrar el contenido de ListView mediante un control GridView
Este ejemplo muestra cómo definir un <xref:System.Windows.Controls.GridView> modo de vista para un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Puede definir el modo de vista de un <xref:System.Windows.Controls.GridView> especificando <xref:System.Windows.Controls.GridViewColumn> objetos. En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.GridViewColumn> objetos que se enlazan al contenido de datos que se especifica para el <xref:System.Windows.Controls.ListView> control. Esto <xref:System.Windows.Controls.GridView> ejemplo especifica tres <xref:System.Windows.Controls.GridViewColumn> objetos que se asignan a la `FirstName`, `LastName`, y `EmployeeNumber` campos de la `EmployeeInfoDataSource` que se establece como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListView> control.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La ilustración siguiente muestra cómo aparece en este ejemplo.  
  
 ![ListView con salida de GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)

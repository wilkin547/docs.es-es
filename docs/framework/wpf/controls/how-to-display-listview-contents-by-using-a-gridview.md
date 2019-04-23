---
title: Procedimiento Mostrar el contenido de ListView mediante un control GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112793"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Procedimiento Mostrar el contenido de ListView mediante un control GridView
En este ejemplo se muestra cómo definir un <xref:System.Windows.Controls.GridView> modo de vista para un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Puede definir el modo de vista de un <xref:System.Windows.Controls.GridView> especificando <xref:System.Windows.Controls.GridViewColumn> objetos. El ejemplo siguiente muestra cómo definir <xref:System.Windows.Controls.GridViewColumn> objetos que se enlazan al contenido de datos que se ha especificado para el <xref:System.Windows.Controls.ListView> control. Esto <xref:System.Windows.Controls.GridView> ejemplo especifica tres <xref:System.Windows.Controls.GridViewColumn> objetos que se asignan a la `FirstName`, `LastName`, y `EmployeeNumber` campos de la `EmployeeInfoDataSource` que se establece como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListView> control.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La siguiente ilustración muestra cómo aparece en este ejemplo.  
  
 ![Captura de pantalla que muestra un ListView con resultado GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Información general sobre ListView](listview-overview.md)
- [Información general sobre GridView](gridview-overview.md)
- [Temas "Cómo..."](listview-how-to-topics.md)

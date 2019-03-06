---
title: Procedimiento Mostrar el contenido de ListView mediante un control GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9a4bcc8b613637521ee91a11b0bdac8f77f90a03
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354406"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Filtrar Mostrar el contenido de ListView mediante un control GridView
En este ejemplo se muestra cómo definir un <xref:System.Windows.Controls.GridView> modo de vista para un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Puede definir el modo de vista de un <xref:System.Windows.Controls.GridView> especificando <xref:System.Windows.Controls.GridViewColumn> objetos. El ejemplo siguiente muestra cómo definir <xref:System.Windows.Controls.GridViewColumn> objetos que se enlazan al contenido de datos que se ha especificado para el <xref:System.Windows.Controls.ListView> control. Esto <xref:System.Windows.Controls.GridView> ejemplo especifica tres <xref:System.Windows.Controls.GridViewColumn> objetos que se asignan a la `FirstName`, `LastName`, y `EmployeeNumber` campos de la `EmployeeInfoDataSource` que se establece como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListView> control.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La siguiente ilustración muestra cómo aparece en este ejemplo.  
  
 ![ListView con salida de GridView](./media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Información general sobre ListView](listview-overview.md)
- [Información general sobre GridView](gridview-overview.md)
- [Temas "Cómo..."](listview-how-to-topics.md)

---
title: Procedimiento Asegurarse de que un GridSplitter es visible
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663317"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Procedimiento Asegurarse de que un GridSplitter es visible
En este ejemplo se muestra cómo asegurarse de que un <xref:System.Windows.Controls.GridSplitter> control no está oculto por los otros controles en un <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Panel.Children%2A> de un <xref:System.Windows.Controls.Grid> control se representan en el orden en que se definen en el marcado o código. <xref:System.Windows.Controls.GridSplitter> se pueden ocultar los controles por otros controles si no se define como los últimos elementos en el <xref:System.Windows.Controls.Panel.Children%2A> colección o si proporcionan otros controles de una mayor <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Para evitar que oculta <xref:System.Windows.Controls.GridSplitter> controles, realice una de las siguientes acciones.  
  
- Asegúrese de que <xref:System.Windows.Controls.GridSplitter> controles son las últimas <xref:System.Windows.Controls.Panel.Children%2A> agregado a la <xref:System.Windows.Controls.Grid>. El ejemplo siguiente se muestra el <xref:System.Windows.Controls.GridSplitter> como el último elemento en el <xref:System.Windows.Controls.Panel.Children%2A> colección de la <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- Establecer el <xref:System.Windows.Controls.Panel.ZIndexProperty> en el <xref:System.Windows.Controls.GridSplitter> encima de un control que podría ocultarlo. El siguiente ejemplo se da el <xref:System.Windows.Controls.GridSplitter> controlar una mayor <xref:System.Windows.Controls.Panel.ZIndexProperty> que el <xref:System.Windows.Controls.Button> control.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- Establezca los márgenes en el control que podría ocultar el <xref:System.Windows.Controls.GridSplitter> para que el <xref:System.Windows.Controls.GridSplitter> se expone. El ejemplo siguiente establece los márgenes de un control que en caso contrario, desea superponer y ocultar el <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.GridSplitter>
- [Temas "Cómo..."](gridsplitter-how-to-topics.md)

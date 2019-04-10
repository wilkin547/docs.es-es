---
title: Filtrar Buscar un TreeViewItem en un TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: 034ec2e57fb3b6a9b3a81f66f6888a68e2c113d7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219049"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Filtrar Buscar un TreeViewItem en un TreeView
El <xref:System.Windows.Controls.TreeView> control proporciona una manera cómoda de mostrar datos jerárquicos. Si su <xref:System.Windows.Controls.TreeView> está enlazado a un origen de datos, el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad proporciona una manera cómoda para que pueda recuperar rápidamente el objeto de datos seleccionado. Normalmente es mejor trabajar con el objeto de datos subyacente, pero a veces es posible que deba manipular mediante programación los datos que contiene <xref:System.Windows.Controls.TreeViewItem>. Por ejemplo, es posible que deba expandir mediante programación el <xref:System.Windows.Controls.TreeViewItem>, o seleccione un elemento diferente en el <xref:System.Windows.Controls.TreeView>.  
  
 Para buscar un <xref:System.Windows.Controls.TreeViewItem> que contiene un objeto de datos específico, deberá recorrer cada nivel de la <xref:System.Windows.Controls.TreeView>. Los elementos de un <xref:System.Windows.Controls.TreeView> también se pueden virtualizar para mejorar el rendimiento. En el caso donde es posible que se puede virtualizar elementos, también debe tener en cuenta un <xref:System.Windows.Controls.TreeViewItem> para comprobar si contiene el objeto de datos.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="description"></a>Descripción  
 El siguiente ejemplo busca un <xref:System.Windows.Controls.TreeView> para un objeto específico y devuelve el objeto contenedor del <xref:System.Windows.Controls.TreeViewItem>. El ejemplo se asegura de que cada <xref:System.Windows.Controls.TreeViewItem> se crea una instancia para que se pueden buscar sus elementos secundarios. En este ejemplo también funciona si el <xref:System.Windows.Controls.TreeView> no utiliza elementos virtualizados.  
  
> [!NOTE]
>  El ejemplo siguiente funciona para cualquier <xref:System.Windows.Controls.TreeView>, independientemente del modelo de datos subyacente y las búsquedas de cada <xref:System.Windows.Controls.TreeViewItem> hasta que se encuentra el objeto. Otra técnica que tiene un mejor rendimiento consiste en Buscar en el modelo de datos para el objeto especificado, realizar un seguimiento de su ubicación dentro de la jerarquía de datos y, a continuación, busque el correspondiente <xref:System.Windows.Controls.TreeViewItem> en el <xref:System.Windows.Controls.TreeView>. Sin embargo, la técnica que tiene un mejor rendimiento requiere un conocimiento del modelo de datos y no se puede generalizar para cualquier <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Código  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 El código anterior se basa en un personalizado <xref:System.Windows.Controls.VirtualizingStackPanel> que expone un método denominado `BringIntoView`. El código siguiente define personalizado <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 El XAML siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> que usa personalizado <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vea también

- [Mejorar el rendimiento de un control TreeView](how-to-improve-the-performance-of-a-treeview.md)

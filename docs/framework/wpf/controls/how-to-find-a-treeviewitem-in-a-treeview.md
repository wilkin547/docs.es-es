---
title: Procedimiento Buscar un TreeViewItem en un TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962093"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Procedimiento Buscar un TreeViewItem en un TreeView
El <xref:System.Windows.Controls.TreeView> control proporciona una manera cómoda de mostrar los datos jerárquicos. Si se enlaza a un origen de datos, la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad proporciona una manera cómoda de recuperar rápidamente el objeto de datos seleccionado. <xref:System.Windows.Controls.TreeView> Normalmente, es mejor trabajar con el objeto de datos subyacente, pero a veces es posible que sea necesario manipular mediante programación los datos que <xref:System.Windows.Controls.TreeViewItem>contiene. Por ejemplo, puede que necesite expandir <xref:System.Windows.Controls.TreeViewItem>mediante programación o seleccionar un elemento diferente en el. <xref:System.Windows.Controls.TreeView>  
  
 Para buscar un <xref:System.Windows.Controls.TreeViewItem> que contenga un objeto <xref:System.Windows.Controls.TreeView>de datos concreto, debe atravesar cada nivel de. Los elementos de un <xref:System.Windows.Controls.TreeView> también se pueden virtualizar para mejorar el rendimiento. En el caso de que se puedan virtualizar los elementos, también debe conocer <xref:System.Windows.Controls.TreeViewItem> un para comprobar si contiene el objeto de datos.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="description"></a>DESCRIPCIÓN  
 <xref:System.Windows.Controls.TreeView> En el ejemplo siguiente se busca un objeto específico y se devuelve el objeto que <xref:System.Windows.Controls.TreeViewItem>contiene. En el ejemplo se garantiza <xref:System.Windows.Controls.TreeViewItem> que se crea una instancia de cada una de ellas para que se puedan buscar sus elementos secundarios. Este ejemplo también funciona si <xref:System.Windows.Controls.TreeView> no usa elementos virtualizados.  
  
> [!NOTE]
> El siguiente ejemplo funciona con cualquier <xref:System.Windows.Controls.TreeView>, independientemente del modelo de datos subyacente, y busca cada <xref:System.Windows.Controls.TreeViewItem> hasta que se encuentra el objeto. Otra técnica que tiene un mejor rendimiento es buscar el objeto especificado en el modelo de datos, realizar un seguimiento de su ubicación dentro de la jerarquía de datos y, <xref:System.Windows.Controls.TreeViewItem> a continuación <xref:System.Windows.Controls.TreeView>, encontrar el correspondiente en el. Sin embargo, la técnica que tiene un mejor rendimiento requiere conocimiento del modelo de datos y no se puede generalizar <xref:System.Windows.Controls.TreeView>para ningún determinado.  
  
## <a name="code"></a>Código  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 El código anterior se basa en un personalizado <xref:System.Windows.Controls.VirtualizingStackPanel> que expone un método denominado. `BringIntoView` En el código siguiente se define <xref:System.Windows.Controls.VirtualizingStackPanel>el personalizado.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 En el código XAML siguiente se muestra cómo <xref:System.Windows.Controls.TreeView> crear un que usa <xref:System.Windows.Controls.VirtualizingStackPanel>el personalizado.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Vea también

- [Mejorar el rendimiento de un control TreeView](how-to-improve-the-performance-of-a-treeview.md)

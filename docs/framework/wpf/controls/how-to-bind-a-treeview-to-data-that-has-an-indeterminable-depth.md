---
title: 'Cómo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458615"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Cómo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable
Puede haber ocasiones en las que desee enlazar un <xref:System.Windows.Controls.TreeView> a un origen de datos cuya profundidad no se conoce.  Esto puede ocurrir cuando los datos son recursivos por naturaleza, como un sistema de archivos, donde las carpetas pueden contener carpetas o la estructura organizativa de una empresa, donde los empleados tienen otros empleados como subordinados directos.  
  
 El origen de datos debe tener un modelo de objetos jerárquico. Por ejemplo, una clase `Employee` podría contener una colección de objetos Employee que son los subordinados directos de un empleado. Si los datos se representan de forma que no son jerárquicos, debe generar una representación jerárquica de los datos.  
  
 Al establecer la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> y si el <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> para cada elemento secundario, el <xref:System.Windows.Controls.ItemsControl> secundario utiliza el mismo <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> que el elemento primario. Por ejemplo, si establece la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> en un <xref:System.Windows.Controls.TreeView>enlazado a datos, cada <xref:System.Windows.Controls.TreeViewItem> que se genere utilizará el <xref:System.Windows.DataTemplate> que se asignó a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> de la <xref:System.Windows.Controls.TreeView>.  
  
 El <xref:System.Windows.HierarchicalDataTemplate> permite especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de una <xref:System.Windows.Controls.TreeViewItem>, o cualquier <xref:System.Windows.Controls.HeaderedItemsControl>, en la plantilla de datos. Al establecer la propiedad <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType>, se utiliza ese valor cuando se aplica el <xref:System.Windows.HierarchicalDataTemplate>. Mediante el uso de un <xref:System.Windows.HierarchicalDataTemplate>, puede establecer de forma recursiva el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de cada <xref:System.Windows.Controls.TreeViewItem> en el <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Controls.TreeView> a datos jerárquicos y usar un <xref:System.Windows.HierarchicalDataTemplate> para especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada <xref:System.Windows.Controls.TreeViewItem>.  La <xref:System.Windows.Controls.TreeView> enlaza a los datos XML que representan a los empleados de una compañía.  Cada elemento `Employee` puede contener otros elementos `Employee` para indicar quién informa a quién. Dado que los datos son recursivos, el <xref:System.Windows.HierarchicalDataTemplate> se puede aplicar a cada nivel.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)

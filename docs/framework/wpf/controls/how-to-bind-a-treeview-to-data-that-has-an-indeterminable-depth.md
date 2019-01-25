---
title: Procedimiento Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 702a86f049635423a31e554d205dcc3cf4aa799d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605372"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Procedimiento Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable
Puede haber ocasiones en que desee enlazar un <xref:System.Windows.Controls.TreeView> a un origen de datos cuya profundidad no se conoce.  Esto puede ocurrir cuando los datos están recursiva por naturaleza, por ejemplo, un sistema de archivos, donde las carpetas pueden contener carpetas, o la estructura organizativa de la empresa, donde los empleados tienen otros empleados como subordinados directos.  
  
 El origen de datos debe tener un modelo de objetos jerárquico. Por ejemplo, un `Employee` clase podría contener una colección de objetos de empleados que son los subordinados directos de un empleado. Si los datos se representan de forma que no es jerárquica, debe generar una representación jerárquica de los datos.  
  
 Al establecer el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> propiedad y si el <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> para cada elemento secundario y, a continuación, el elemento secundario <xref:System.Windows.Controls.ItemsControl> usa el mismo <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> como elemento primario. Por ejemplo, si establece la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad en un enlace de datos <xref:System.Windows.Controls.TreeView>, cada <xref:System.Windows.Controls.TreeViewItem> que es generado usa el <xref:System.Windows.DataTemplate> que se asignó a la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad de la <xref:System.Windows.Controls.TreeView>.  
  
 El <xref:System.Windows.HierarchicalDataTemplate> le permite especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para un <xref:System.Windows.Controls.TreeViewItem>, o cualquier <xref:System.Windows.Controls.HeaderedItemsControl>, en la plantilla de datos. Al establecer el <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> propiedad, que es el valor se usa cuando el <xref:System.Windows.HierarchicalDataTemplate> se aplica. Mediante el uso de un <xref:System.Windows.HierarchicalDataTemplate>, puede que el conjunto de forma recursiva el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada <xref:System.Windows.Controls.TreeViewItem> en el <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Controls.TreeView> en datos jerárquicos y usar un <xref:System.Windows.HierarchicalDataTemplate> para especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada <xref:System.Windows.Controls.TreeViewItem>.  El <xref:System.Windows.Controls.TreeView> se enlaza a datos XML que representan los empleados de una empresa.  Cada `Employee` elemento puede contener otros `Employee` elementos para indicar que informa a quién. Dado que los datos están recursiva, la <xref:System.Windows.HierarchicalDataTemplate> se pueden aplicar a cada nivel.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)

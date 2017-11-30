---
title: "Cómo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b16cae3a91eae73a4480484d89bb075862256b25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Cómo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable
Puede haber ocasiones cuando desea enlazar un <xref:System.Windows.Controls.TreeView> a un origen de datos cuya profundidad no se conoce.  Esto puede ocurrir cuando los datos están recursiva por naturaleza, como un sistema de archivos, donde las carpetas pueden contener carpetas, o la estructura organizativa de la empresa, donde los empleados tienen otros empleados como subordinados directos.  
  
 El origen de datos debe tener un modelo de objetos jerárquico. Por ejemplo, un `Employee` clase puede contener una colección de objetos de empleados que son los informes directos de un empleado. Si los datos se representan de forma que no es jerárquica, deberá generar una representación jerárquica de los datos.  
  
 Al establecer el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> propiedad y si la <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> para cada elemento secundario y, a continuación, el elemento secundario <xref:System.Windows.Controls.ItemsControl> utiliza la misma <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> como elemento primario. Por ejemplo, si establece la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad en un enlace de datos <xref:System.Windows.Controls.TreeView>, cada <xref:System.Windows.Controls.TreeViewItem> decir generado utiliza el <xref:System.Windows.DataTemplate> que se asignó a la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad de la <xref:System.Windows.Controls.TreeView>.  
  
 El <xref:System.Windows.HierarchicalDataTemplate> le permite especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para un <xref:System.Windows.Controls.TreeViewItem>, o cualquier <xref:System.Windows.Controls.HeaderedItemsControl>, en la plantilla de datos. Al establecer el <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> propiedad, que es el valor se usa cuando el <xref:System.Windows.HierarchicalDataTemplate> se aplica. Mediante el uso de un <xref:System.Windows.HierarchicalDataTemplate>, puede que el conjunto de forma recursiva el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada <xref:System.Windows.Controls.TreeViewItem> en el <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Controls.TreeView> a datos jerárquicos y use un <xref:System.Windows.HierarchicalDataTemplate> para especificar el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada <xref:System.Windows.Controls.TreeViewItem>.  El <xref:System.Windows.Controls.TreeView> se enlaza a datos XML que representan a los empleados de una empresa.  Cada `Employee` elemento puede contener otros `Employee` elementos para indicar a quién informa a quién. Dado que los datos son recursivos, el <xref:System.Windows.HierarchicalDataTemplate> puede aplicarse a cada nivel.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)

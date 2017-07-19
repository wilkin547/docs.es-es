---
title: "C&#243;mo: Crear controles ListViewItems con un control CheckBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles ListView"
  - "controles de casilla de verificación"
  - "Controles de ListView, controles de casilla de verificación"
  - "CheckBox (control), control ListView"
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear controles ListViewItems con un control CheckBox
Este ejemplo muestra cómo mostrar una columna de <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Ejemplo  
 Para crear una columna que contiene <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView>, cree un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>. A continuación, establezca el <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> de un <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.  
  
 El ejemplo siguiente muestra un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>. El ejemplo se enlaza la <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> propiedad de la <xref:System.Windows.Controls.CheckBox> a la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valor de propiedad de la <xref:System.Windows.Controls.ListViewItem> que lo contiene. Por lo tanto, cuando la <xref:System.Windows.Controls.ListViewItem> que contiene el <xref:System.Windows.Controls.CheckBox> está seleccionada, el <xref:System.Windows.Controls.CheckBox> está activada.  
  
 [!code-xml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 En el ejemplo siguiente se muestra cómo crear una columna de <xref:System.Windows.Controls.CheckBox> controles. Convertir la columna, el ejemplo establece la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad de la <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Control>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
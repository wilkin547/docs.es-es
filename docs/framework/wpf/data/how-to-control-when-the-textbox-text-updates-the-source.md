---
title: "C&#243;mo: Controlar cu&#225;ndo el texto de TextBox actualiza el origen | Microsoft Docs"
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
  - "enlace de datos, control de tiempo de las actualizaciones de origen"
  - "actualizaciones de origen, control de tiempo"
  - "control de tiempo de las actualizaciones de origen"
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Controlar cu&#225;ndo el texto de TextBox actualiza el origen
En este tema se describe cómo utilizar la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> para controlar el control de tiempo de las actualizaciones del [origen de enlace](GTMT).  En el tema se utiliza el control <xref:System.Windows.Controls.TextBox> como ejemplo.  
  
## Ejemplo  
 El valor predeterminado de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> de la propiedad <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> es <xref:System.Windows.Data.UpdateSourceTrigger>.  Esto significa que si una aplicación tiene un objeto <xref:System.Windows.Controls.TextBox> con una propiedad <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> enlazada a datos, el siguiente texto que se escriba en <xref:System.Windows.Controls.TextBox> no actualizará el origen de enlace hasta que <xref:System.Windows.Controls.TextBox> pierda el foco \(por ejemplo, cuando haga clic fuera de <xref:System.Windows.Controls.TextBox>\).  
  
 Si desea que el origen se actualice a medida que se escribe, debe establecer la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace en <xref:System.Windows.Data.UpdateSourceTrigger>.  En el ejemplo siguiente, las propiedades `Text` de <xref:System.Windows.Controls.TextBox> y de <xref:System.Windows.Controls.TextBlock> están enlazadas a la misma propiedad de origen.  La propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace de <xref:System.Windows.Controls.TextBox> está establecida en <xref:System.Windows.Data.UpdateSourceTrigger>.  
  
 [!code-xml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 Como resultado, <xref:System.Windows.Controls.TextBlock> muestra el mismo texto \(dado que el origen cambia\) a medida que el usuario escribe texto en <xref:System.Windows.Controls.TextBox>, como se muestra en la captura de pantalla siguiente del ejemplo:  
  
 ![Captura de pantalla de ejemplo de enlace de datos simple](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Si tiene un cuadro de diálogo o un formulario modificable por el usuario y desea diferir las actualizaciones del origen hasta que el usuario haya terminado de modificar los campos y haga clic en "Aceptar", puede establecer el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> de los enlaces en <xref:System.Windows.Data.UpdateSourceTrigger>, como en el ejemplo siguiente:  
  
 [!code-xml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Cuando se establece el valor de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> en <xref:System.Windows.Data.UpdateSourceTrigger>, el valor del origen cambia únicamente cuando la aplicación llama al método <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>.  En el siguiente ejemplo se muestra cómo llamar a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> para `itemNameTextBox`.  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Puede utilizar la misma técnica para las propiedades de otros controles, pero debe tener presente que el valor predeterminado de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> de la mayoría de las demás propiedades es <xref:System.Windows.Data.UpdateSourceTrigger>.  Para obtener más información, consulte la página de propiedades <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> se encarga de las actualizaciones del origen y, por consiguiente, únicamente es pertinente para los enlaces <xref:System.Windows.Data.BindingMode> o <xref:System.Windows.Data.BindingMode>.  Para que los enlaces <xref:System.Windows.Data.BindingMode> y <xref:System.Windows.Data.BindingMode> funcionen, el objeto de origen debe proporcionar notificaciones de cambio de propiedad.  Puede consultar los ejemplos citados en este tema para obtener más información.  Además, puede consultar [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
## Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
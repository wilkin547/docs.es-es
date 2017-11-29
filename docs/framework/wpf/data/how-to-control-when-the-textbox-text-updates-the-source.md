---
title: "Cómo: Controlar cuándo el texto de TextBox actualiza el origen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Cómo: Controlar cuándo el texto de TextBox actualiza el origen
Este tema describe cómo utilizar el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad para controlar el tiempo de las actualizaciones del origen de enlace. El tema utiliza el <xref:System.Windows.Controls.TextBox> control como un ejemplo.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valo <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Esto significa que si una aplicación tiene un <xref:System.Windows.Controls.TextBox> con un enlace de datos <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad, el texto que escriba en el <xref:System.Windows.Controls.TextBox> no actualiza el origen hasta el <xref:System.Windows.Controls.TextBox> pierde el foco (por ejemplo, al hacer clic fuera del <xref:System.Windows.Controls.TextBox>).  
  
 Si desea que el origen se actualizara como escribir, establezca el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace a <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. En el ejemplo siguiente, la `Text` propiedades de la <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> están enlazados a la misma propiedad de origen. El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad de la <xref:System.Windows.Controls.TextBox> enlace se establece en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 Como resultado, el <xref:System.Windows.Controls.TextBlock> muestra el mismo texto (dado que el origen cambia) cuando el usuario escribe texto en el <xref:System.Windows.Controls.TextBox>, tal y como se muestra en la siguiente captura de pantalla del ejemplo:  
  
 ![Captura de pantalla de ejemplo del enlace de datos simple](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Si tiene un cuadro de diálogo o un formulario puede modificar el usuario y desee diferir las actualizaciones del origen hasta que el usuario ha terminado de editar los campos y hace clic en "Aceptar", puede establecer la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor de sus enlaces a <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, como en el ejemplo siguiente:  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Al establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, solo se cambia el valor de origen cuando la aplicación llama el <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> método. En el ejemplo siguiente se muestra cómo llamar a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> para `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Puede usar la misma técnica para las propiedades de otros controles, pero tenga en cuenta que la mayoría de las demás propiedades tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valo <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Para obtener más información, consulte la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> página de propiedades.  
  
> [!NOTE]
>  El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad trabaja con las actualizaciones del origen y, por tanto, solo es pertinente para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces. Para <xref:System.Windows.Data.BindingMode.TwoWay> y <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces funcione, las necesidades de objeto de origen para proporcionar notificaciones de cambio de propiedad. Puede consultar los ejemplos citados en este tema para obtener más información. Además, puede consultar [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Vea también  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

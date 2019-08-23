---
title: Procedimiento Controlar cuándo el texto de TextBox actualiza el origen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: d1d624d7550a1135431b7fffc7450e3a510855a7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966448"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Procedimiento Controlar cuándo el texto de TextBox actualiza el origen
En este tema se describe cómo utilizar <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> la propiedad para controlar el tiempo de las actualizaciones del origen de enlace. En el tema se <xref:System.Windows.Controls.TextBox> usa el control como ejemplo.  
  
## <a name="example"></a>Ejemplo  
 El elemento de lenguaje <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> la propiedad tiene un <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor predeterminado <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>de. Esto significa que si una aplicación tiene <xref:System.Windows.Controls.TextBox> un con un enlace <xref:System.Windows.Controls.TextBox>de datos.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad, el texto que escribe en <xref:System.Windows.Controls.TextBox> no actualiza el origen <xref:System.Windows.Controls.TextBox> hasta que pierde el foco (por ejemplo, al hacer clic fuera de la <xref:System.Windows.Controls.TextBox>).  
  
 Si desea que el origen se actualice a medida que escribe, establezca el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace en. <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> En el ejemplo siguiente, las líneas de código resaltadas muestran `Text` que las propiedades de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> están enlazadas a la misma propiedad de origen. La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>del enlace está establecida en. <xref:System.Windows.Controls.TextBox>  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Como resultado, <xref:System.Windows.Controls.TextBlock> muestra el mismo texto (porque el origen cambia) cuando el usuario escribe texto en el <xref:System.Windows.Controls.TextBox>, como se muestra en la siguiente captura de pantalla del ejemplo:  
  
 ![Captura de pantalla que muestra el enlace de datos simple.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)  
  
 Si tiene un cuadro de diálogo o un formulario editable por el usuario y desea aplazar las actualizaciones de origen hasta que el usuario haya terminado de editar los campos y haga clic en " <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> aceptar", puede establecer el <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>valor de los enlaces en, como en el ejemplo siguiente:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Al establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor en <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, el valor de origen solo cambia cuando la aplicación llama al <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> método. En el ejemplo siguiente se muestra cómo <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> llamar `itemNameTextBox`a para:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
> Puede usar la misma técnica para las propiedades de otros controles, pero tenga en cuenta que la mayoría de las demás propiedades <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> tienen un <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>valor predeterminado de. Para obtener más información, vea <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> la página de propiedades.  
  
> [!NOTE]
> La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad trata las actualizaciones de origen y, por tanto, <xref:System.Windows.Data.BindingMode.TwoWay> solo <xref:System.Windows.Data.BindingMode.OneWayToSource> es pertinente para los enlaces o. Para <xref:System.Windows.Data.BindingMode.TwoWay> que <xref:System.Windows.Data.BindingMode.OneWayToSource> los enlaces y funcionen, el objeto de origen debe proporcionar notificaciones de cambio de propiedad. Puede consultar los ejemplos citados en este tema para obtener más información. Además, puede consultar [Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](data-binding-how-to-topics.md)

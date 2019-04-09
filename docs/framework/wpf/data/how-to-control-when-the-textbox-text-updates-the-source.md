---
title: Filtrar Controlar cuándo el texto de TextBox actualiza el origen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 5272a19f69b3caf80fd7d5187c9a6a386cd44621
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143278"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Filtrar Controlar cuándo el texto de TextBox actualiza el origen
Este tema describe cómo usar el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad para controlar la temporización de las actualizaciones del origen de enlace. Este tema se usa el <xref:System.Windows.Controls.TextBox> control como un ejemplo.  
  
## <a name="example"></a>Ejemplo  
 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Esto significa que si una aplicación tiene un <xref:System.Windows.Controls.TextBox> con un enlace de datos <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propiedad, el texto que escriba en el <xref:System.Windows.Controls.TextBox> no actualiza el origen hasta el <xref:System.Windows.Controls.TextBox> pierde el foco (por ejemplo, al hacer clic en fuera de la <xref:System.Windows.Controls.TextBox>).  
  
 Si desea que el origen de actualizarse a medida que escribe, establezca el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace a <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. En el ejemplo siguiente, las líneas de código resaltadas muestran que el `Text` propiedades de la <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> están enlazados a la misma propiedad de origen. El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad de la <xref:System.Windows.Controls.TextBox> enlace está establecido en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Como resultado, el <xref:System.Windows.Controls.TextBlock> muestra el mismo texto (dado que el origen cambia) como el usuario escribe texto en el <xref:System.Windows.Controls.TextBox>, tal y como se muestra en la siguiente captura de pantalla del ejemplo:  
  
 ![Captura de pantalla de ejemplo de enlace de datos simple](./media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Si tiene un cuadro de diálogo o un formulario modificable por el usuario y desea diferir las actualizaciones de origen hasta que el usuario ha terminado de editar los campos y hace clic en "Aceptar", puede establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor de los enlaces en <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, como en el ejemplo siguiente:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Al establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, el valor de origen cambia solo cuando la aplicación llama el <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> método. El ejemplo siguiente muestra cómo llamar a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> para `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Puede usar la misma técnica para las propiedades de otros controles, pero tenga en cuenta que la mayoría de las propiedades tiene un valor predeterminado <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Para obtener más información, consulte la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> página de propiedades.  
  
> [!NOTE]
>  El <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> se ocupa de las actualizaciones del origen de propiedad y, por tanto, solo es pertinente para <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces. Para <xref:System.Windows.Data.BindingMode.TwoWay> y <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces funcione, el objeto de origen debe proporcionar notificaciones de cambio de propiedad. Puede consultar los ejemplos citados en este tema para obtener más información. Además, puede consultar [Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](data-binding-how-to-topics.md)

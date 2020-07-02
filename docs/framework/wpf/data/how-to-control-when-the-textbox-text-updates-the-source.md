---
title: 'Cómo: Controlar cuándo el texto de TextBox actualiza el origen'
description: Controlar el tiempo de las actualizaciones del origen de enlace mediante la propiedad UpdateSourceTrigger en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 8f6eb5beb0d14a951f6e6cf6eb81e130f5a3e194
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622788"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Cómo: Controlar cuándo el texto de TextBox actualiza el origen
En este tema se describe cómo utilizar la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad para controlar el tiempo de las actualizaciones del origen de enlace. En el tema se usa el <xref:System.Windows.Controls.TextBox> control como ejemplo.

## <a name="example"></a>Ejemplo
 La <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> propiedad tiene un <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> . Esto significa que si una aplicación tiene un <xref:System.Windows.Controls.TextBox> con una propiedad enlazada a datos <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> , el texto que escribe en no <xref:System.Windows.Controls.TextBox> actualiza el origen hasta que <xref:System.Windows.Controls.TextBox> pierde el foco (por ejemplo, al hacer clic fuera de la <xref:System.Windows.Controls.TextBox> ).

 Si desea que el origen se actualice a medida que escribe, establezca el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del enlace en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . En el ejemplo siguiente, las líneas de código resaltadas muestran que las `Text` propiedades de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> están enlazadas a la misma propiedad de origen. La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad del <xref:System.Windows.Controls.TextBox> enlace está establecida en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 Como resultado, <xref:System.Windows.Controls.TextBlock> muestra el mismo texto (porque el origen cambia) cuando el usuario escribe texto en el <xref:System.Windows.Controls.TextBox> , como se muestra en la siguiente captura de pantalla del ejemplo:

 ![Captura de pantalla que muestra el enlace de datos simple.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Si tiene un cuadro de diálogo o un formulario editable por el usuario y desea aplazar las actualizaciones de origen hasta que el usuario haya terminado de editar los campos y haga clic en "Aceptar", puede establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor de los enlaces en <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , como en el ejemplo siguiente:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Al establecer el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor en <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , el valor de origen solo cambia cuando la aplicación llama al <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> método. En el ejemplo siguiente se muestra cómo llamar a <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> para `itemNameTextBox` :

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> Puede usar la misma técnica para las propiedades de otros controles, pero tenga en cuenta que la mayoría de las demás propiedades tienen un <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valor predeterminado de <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Para obtener más información, vea la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Página de propiedades.

> [!NOTE]
> La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad trata las actualizaciones de origen y, por tanto, solo es pertinente para los <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> enlaces o. Para <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> que los enlaces y funcionen, el objeto de origen debe proporcionar notificaciones de cambio de propiedad. Puede consultar los ejemplos citados en este tema para obtener más información. Además, puede consultar [Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).

## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](data-binding-how-to-topics.md)

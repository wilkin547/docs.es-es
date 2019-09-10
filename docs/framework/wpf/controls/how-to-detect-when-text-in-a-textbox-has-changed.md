---
title: Procedimiento Detectar cuándo cambia el texto en un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855621"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Procedimiento Detectar cuándo cambia el texto en un control TextBox

En este ejemplo se muestra una manera de <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> utilizar el evento para ejecutar un método cada vez que <xref:System.Windows.Controls.TextBox> el texto de un control ha cambiado.

En la clase [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código subyacente del que contiene el <xref:System.Windows.Controls.TextBox> control en el que desea supervisar los cambios, inserte un método al que llamar cada vez <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> que se desencadene el evento.  Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.

Se llama al controlador de eventos cada vez que se <xref:System.Windows.Controls.TextBox> cambia el contenido del control, ya sea por un usuario o mediante programación.

> [!NOTE]
> Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.

## <a name="example"></a>Ejemplo

En que define el control, especifique el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método del controlador de eventos. <xref:System.Windows.Controls.TextBox> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Ejemplo

En la clase [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código subyacente del que contiene el <xref:System.Windows.Controls.TextBox> control en el que desea supervisar los cambios, inserte un método al que llamar cada vez <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> que se desencadene el evento.  Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Se llama al controlador de eventos cada vez que se <xref:System.Windows.Controls.TextBox> cambia el contenido del control, ya sea por un usuario o mediante programación.

> [!NOTE]
> Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.

Comentarios

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Información general sobre TextBox](textbox-overview.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)

---
title: 'Cómo: Detectar cuándo cambia el texto en un control TextBox'
description: Aprenda a usar el evento TextChanged para ejecutar un método cada vez que el texto de un control TextBox cambie en una aplicación Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166229"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Cómo: Detectar cuándo cambia el texto en un control TextBox

En este ejemplo se muestra una manera de utilizar el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento para ejecutar un método cada vez que el texto de un <xref:System.Windows.Controls.TextBox> control ha cambiado.

En la clase de código subyacente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control en el que <xref:System.Windows.Controls.TextBox> desea supervisar los cambios, inserte un método al que llamar cada vez que se <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadene el evento.  Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.

Se llama al controlador de eventos cada vez que se cambia el contenido del <xref:System.Windows.Controls.TextBox> control, ya sea por un usuario o mediante programación.

> [!NOTE]
> Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.

## <a name="example"></a>Ejemplo

En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define el <xref:System.Windows.Controls.TextBox> control, especifique el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método del controlador de eventos.

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Ejemplo

En la clase de código subyacente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el control en el que <xref:System.Windows.Controls.TextBox> desea supervisar los cambios, inserte un método al que llamar cada vez que se <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadene el evento.  Este método debe tener una firma que coincida con lo que el <xref:System.Windows.Controls.TextChangedEventHandler> delegado espera.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Se llama al controlador de eventos cada vez que se cambia el contenido del <xref:System.Windows.Controls.TextBox> control, ya sea por un usuario o mediante programación.

> [!NOTE]
> Este evento se desencadena cuando <xref:System.Windows.Controls.TextBox> se crea el control y se rellena inicialmente con texto.

Comentarios

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)

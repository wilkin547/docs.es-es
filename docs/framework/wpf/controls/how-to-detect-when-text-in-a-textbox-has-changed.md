---
title: "Cómo: Detectar cuándo cambia el texto en un control TextBox"
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
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92fc8995ab75cc25bac3bb21b1646052822c3721
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Cómo: Detectar cuándo cambia el texto en un control TextBox
Este ejemplo muestra cómo usar la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento para ejecutar un método cada vez que el texto de un <xref:System.Windows.Controls.TextBox> control ha cambiado.  
  
 En la clase de código subyacente para la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, inserte un método al que llamar cuando la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.  Este método debe tener una firma que coincida con lo que se espera por el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.  
  
 Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control se cambian, por un usuario o mediante programación.  
  
 **Nota:** este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.  
  
## <a name="example"></a>Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define su <xref:System.Windows.Controls.TextBox> controlar, especifique la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> atributo con un valor que coincida con el nombre del método de controlador de eventos.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>Ejemplo  
 En la clase de código subyacente para la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que contiene el <xref:System.Windows.Controls.TextBox> control que desea supervisar para realizar cambios, inserte un método al que llamar cuando la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> desencadena el evento.  Este método debe tener una firma que coincida con lo que se espera por el <xref:System.Windows.Controls.TextChangedEventHandler> delegar.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Se llama al controlador de eventos cada vez que el contenido de la <xref:System.Windows.Controls.TextBox> control se cambian, por un usuario o mediante programación.  
  
 **Nota:** este evento desencadena cuando el <xref:System.Windows.Controls.TextBox> control se crea y se rellena inicialmente con el texto.  
  
 Comentarios  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)

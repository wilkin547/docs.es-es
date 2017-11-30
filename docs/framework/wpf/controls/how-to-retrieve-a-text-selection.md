---
title: "Cómo: Recuperar una selección de texto"
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d5e1c362c02d2d1d9e1840ea2a55df6875a80ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-a-text-selection"></a>Cómo: Recuperar una selección de texto
Este ejemplo muestra cómo usar la <xref:System.Windows.Controls.TextBox.SelectedText%2A> propiedad que se va a recuperar el texto que el usuario ha seleccionado en un <xref:System.Windows.Controls.TextBox> control.  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra la definición de un <xref:System.Windows.Controls.TextBox> control que contiene el texto que desea seleccionar, y un <xref:System.Windows.Controls.Button> control con un determinado <xref:System.Windows.Controls.Button.OnClick%2A> método.  
  
 En este ejemplo, un botón con un asociado <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos se usa para recuperar la selección de texto. Cuando el usuario hace clic en el botón, el <xref:System.Windows.Controls.Button.OnClick%2A> método copia cualquier texto seleccionado en el cuadro de texto en una cadena. Los casos especiales de forma que la selección de texto se recupera (hacer clic en un botón), así como la acción realizada con esa selección (copiar la selección de texto en una cadena), pueden modificarse fácilmente para adaptarse a una amplia variedad de escenarios.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] en el ejemplo se muestra un <xref:System.Windows.Controls.Button.OnClick%2A> controlador de eventos para el botón definido en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para este ejemplo.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)

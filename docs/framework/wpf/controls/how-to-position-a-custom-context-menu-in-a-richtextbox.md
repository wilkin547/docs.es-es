---
title: 'Cómo: Colocar un menú contextual personalizado en un control RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: bde28cdb87bdaef3198d1efd3059fed3d0ae0ce2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553863"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>Cómo: Colocar un menú contextual personalizado en un control RichTextBox
Este ejemplo muestra cómo colocar un menú contextual personalizado para un <xref:System.Windows.Controls.RichTextBox>.  
  
 Cuando se implementa un menú contextual personalizado para un control **RichTextBox**, es responsable del control de la posición del menú contextual.  De forma predeterminada, se abre un menú contextual personalizado en el centro del control **RichTextBox**.  
  
## <a name="example"></a>Ejemplo  
 Para invalidar el comportamiento de selección de ubicación predeterminado, agregue un agente de escucha para el <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> eventos.  En el ejemplo siguiente se muestra hacer esto mediante programación.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una implementación correspondiente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> agente de escucha de eventos.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>Vea también  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)

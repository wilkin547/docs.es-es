---
title: "Cómo: Colocar un menú contextual personalizado en un control RichTextBox"
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
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c0a4fd8d2df15dcca2d9d1751f3089922d9a5ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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

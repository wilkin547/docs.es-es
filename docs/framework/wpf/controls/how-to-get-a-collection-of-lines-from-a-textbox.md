---
title: "Cómo: Obtener una colección de líneas de un control TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12d32266bb901f6ce47d19d92d6f0785277aa7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Cómo: Obtener una colección de líneas de un control TextBox
Este ejemplo muestra cómo obtener una colección de líneas de texto de un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un método simple que toma un <xref:System.Windows.Controls.TextBox> como argumento y devuelve un <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto en el **cuadro de texto**.  El <xref:System.Windows.Controls.TextBox.LineCount%2A> propiedad se utiliza para determinar el número de líneas que está actualmente en el **cuadro de texto**y el <xref:System.Windows.Controls.TextBox.GetLineText%2A> , a continuación, se utiliza el método para extraer cada línea y agregarla a la colección de líneas.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)

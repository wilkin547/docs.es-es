---
title: "Cómo: Definir una plantilla de un control GroupBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b6312575dbf44b7c4ae872fbb87df41eb2e32ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-groupbox-template"></a>Cómo: Definir una plantilla de un control GroupBox
Este ejemplo muestra cómo crear una plantilla para un <xref:System.Windows.Controls.GroupBox> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Controls.GroupBox> plantilla de control mediante una <xref:System.Windows.Controls.Grid> control de diseño. La plantilla utiliza un <xref:System.Windows.Controls.BorderGapMaskConverter> para definir el borde de la <xref:System.Windows.Controls.GroupBox> para que el borde no oculte el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> contenido.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GroupBox>  
 [Temas de procedimientos de control GroupBox](http://msdn.microsoft.com/en-us/7692e155-a4c6-428c-b7e0-64b3740daca7)

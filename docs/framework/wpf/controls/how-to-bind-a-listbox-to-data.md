---
title: "Cómo: Enlazar a datos un control ListBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: deb5e05a7c48f26d0b829ba75b4ae120841e0a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-listbox-to-data"></a>Cómo: Enlazar a datos un control ListBox
Puede crear un programador de aplicaciones <xref:System.Windows.Controls.ListBox> controles sin especificar el contenido de cada <xref:System.Windows.Controls.ListBoxItem> por separado. Puede utilizar el enlace de datos para enlazar datos a los elementos individuales.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.ListBox> que rellena la <xref:System.Windows.Controls.ListBoxItem> elementos mediante un enlace de datos a un origen de datos denominado *colores*. En este caso no es necesario utilizar <xref:System.Windows.Controls.ListBoxItem> etiquetas para especificar el contenido de cada elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)

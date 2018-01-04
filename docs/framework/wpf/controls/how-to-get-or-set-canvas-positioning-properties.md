---
title: "Cómo: Obtener o establecer propiedades de situación de Canvas"
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
helpviewer_keywords: Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2b01657088c388ad09037716278dc0788de2abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Cómo: Obtener o establecer propiedades de situación de Canvas
Este ejemplo muestra cómo utilizar los métodos de colocación de la <xref:System.Windows.Controls.Canvas> elemento que se va a colocar el contenido secundario. Este ejemplo utiliza el contenido de un <xref:System.Windows.Controls.ListBoxItem> para representar valores de posición y convierte los valores a las instancias de <xref:System.Double>, que es un argumento necesario para determinar la posición. Los valores, a continuación, se convierten en cadenas y se muestran como texto en un <xref:System.Windows.Controls.TextBlock> elemento mediante la <xref:System.Windows.Controls.Canvas.GetLeft%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> elemento que tiene once seleccionable <xref:System.Windows.Controls.ListBoxItem> elementos. El <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> desencadenadores de eventos el `ChangeLeft` método personalizado, que define el bloque de código siguiente.  
  
 Cada <xref:System.Windows.Controls.ListBoxItem> representa un <xref:System.Double> valor, que es uno de los argumentos que el <xref:System.Windows.Controls.Canvas.SetLeft%2A> método <xref:System.Windows.Controls.Canvas> acepta. Para poder usar un <xref:System.Windows.Controls.ListBoxItem> para representar una instancia de <xref:System.Double>, primero debe convertir el <xref:System.Windows.Controls.ListBoxItem> para el tipo de datos correcto.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Cuando un usuario cambia el <xref:System.Windows.Controls.ListBox> selección, invoca el `ChangeLeft` método personalizado. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a una <xref:System.Windows.LengthConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double> (tenga en cuenta que este valor ya se ha convertido en un <xref:System.String> mediante el uso de la <xref:System.Windows.Controls.Control.ToString%2A> método). Este valor, a continuación, se ha pasado a la <xref:System.Windows.Controls.Canvas.SetLeft%2A> y <xref:System.Windows.Controls.Canvas.GetLeft%2A> métodos de <xref:System.Windows.Controls.Canvas> con el fin de cambiar la posición de la `text1` objeto.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

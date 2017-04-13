---
title: "C&#243;mo: Crear un efecto de activaci&#243;n mediante eventos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "colores de los elementos, cambiar"
  - "colores de los elementos, cambiar"
  - "efecto de activación"
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear un efecto de activaci&#243;n mediante eventos
En este ejemplo se muestra cómo cambiar el color de un elemento cuando el puntero del mouse entra y sale del área ocupada por el elemento.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
> [!NOTE]
>  En este ejemplo se muestra cómo utilizar los eventos, pero la manera recomendada de lograr este mismo efecto es utilizar <xref:System.Windows.Trigger> en un estilo.  Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Ejemplo  
 En el [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] siguiente se crea la interfaz de usuario, que está compuesta de un objeto <xref:System.Windows.Controls.Border> alrededor de un objeto <xref:System.Windows.Controls.TextBlock>, y se asocian los controladores de eventos <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> a <xref:System.Windows.Controls.Border>.  
  
 [!code-xml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 En el siguiente código subyacente se crean los controladores de eventos <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave>.  Cuando el puntero del mouse entra en el objeto <xref:System.Windows.Controls.Border>, el fondo de <xref:System.Windows.Controls.Border> se cambia al color rojo.  Cuando el puntero del mouse sale del objeto <xref:System.Windows.Controls.Border>, el fondo de <xref:System.Windows.Controls.Border> se vuelve a establecer en el color blanco.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
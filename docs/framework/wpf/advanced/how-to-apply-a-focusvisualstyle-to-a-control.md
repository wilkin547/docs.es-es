---
title: "C&#243;mo: Aplicar FocusVisualStyle a un control | Microsoft Docs"
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
  - "FocusVisualStyle (propiedad)"
  - "propiedades, FocusVisualStyle"
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Aplicar FocusVisualStyle a un control
En este ejemplo se muestra cómo crear un estilo visual de foco en los recursos y aplicar el estilo a un control, utilizando la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se define un estilo que crea una composición de controles adicional que se aplica únicamente cuando ese control recibe el foco del teclado en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Para ello, se define un estilo con <xref:System.Windows.Controls.ControlTemplate>, y luego se hace referencia a ese estilo como un recurso al establecer la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Un rectángulo externo que parece un borde se coloca fuera del área rectangular.  A menos que se modifique de otro modo, la operación de ajuste de tamaño del estilo utiliza las propiedades <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular donde se aplica el estilo visual de foco.  En este ejemplo se establecen valores negativos para <xref:System.Windows.FrameworkElement.Margin%2A>, a fin de que el borde parezca ligeramente fuera del control que tiene el foco.  
  
 [!code-xml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> se aplica además de cualquier estilo de plantilla de control que proceda de un estilo explícito o de un estilo de tema; sigue siendo posible crear el estilo primario de un control mediante <xref:System.Windows.Controls.ControlTemplate> y estableciendo ese estilo en la propiedad <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 Los estilos visuales de foco deben utilizarse de manera coherente en un tema o una interfaz de usuario, en lugar de utilizar uno diferente para cada elemento que pueda recibir el foco.  Para obtener información detallada, vea [Aplicar estilo a los controles al recibir el foco y FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Aplicar estilo a los controles al recibir el foco y FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
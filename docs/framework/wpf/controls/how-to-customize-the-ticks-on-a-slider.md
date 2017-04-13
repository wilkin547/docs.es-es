---
title: "C&#243;mo: Personalizar las marcas de paso en un control Slider | Microsoft Docs"
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
  - "TickBar"
  - "Control deslizante, crear con TickBar"
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Personalizar las marcas de paso en un control Slider
Este ejemplo muestra cómo crear un <xref:System.Windows.Controls.Slider> control que tiene las marcas de graduación.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Primitives.TickBar> muestra cuando se establece la <xref:System.Windows.Controls.Slider.TickPlacement%2A> propiedad en un valor distinto de <xref:System.Windows.Controls.Primitives.TickPlacement>, que es el valor predeterminado.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.Slider> con una <xref:System.Windows.Controls.Primitives.TickBar> que muestra marcas de graduación. El <xref:System.Windows.Controls.Slider.TickPlacement%2A> y <xref:System.Windows.Controls.Slider.TickFrequency%2A> propiedades definen la ubicación de las marcas de graduación y el intervalo entre ellos. Cuando se mueve el <xref:System.Windows.Controls.Primitives.Thumb>, información sobre herramientas muestra el valor de la <xref:System.Windows.Controls.Slider>. El <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> propiedad define dónde se producen las informaciones sobre herramientas. El <xref:System.Windows.Controls.Primitives.Thumb> movimientos corresponden a la ubicación de las marcas de graduación porque <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> está establecido en `true`.  
  
 En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Controls.Slider.Ticks%2A> propiedad que se va a crear a lo largo de las marcas de graduación la <xref:System.Windows.Controls.Slider> a intervalos irregulares.  
  
 [!code-xml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Slider>   
 <xref:System.Windows.Controls.Primitives.TickBar>   
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>   
 [Temas de procedimientos de control deslizante](http://msdn.microsoft.com/es-es/534be86c-afb2-425d-8186-631278a9925e)
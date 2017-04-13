---
title: "C&#243;mo: Usar colores del sistema en un degradado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "degradados, colores del sistema en"
  - "colores del sistema en degradados"
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Usar colores del sistema en un degradado
Para utilizar un color del sistema en un degradado, se utilizan las propiedades estáticas *\<SystemColor\>*Color y *\<SystemColor\>*ColorKey de la clase <xref:System.Windows.SystemColors> para obtener una referencia al color, donde *\<SystemColor\>* es el nombre del color del sistema deseado.  Utilice las propiedades *\<SystemColor\>*ColorKey cuando desee crear una referencia dinámica que se actualice automáticamente al cambiar el tema del sistema.  De lo contrario, utilice las propiedades *\<SystemColor\>*Color.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan recursos de colores del sistema dinámicos para crear un degradado.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 En el ejemplo siguiente se utilizan recursos de colores del sistema estáticos para crear un degradado.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.SystemColors>   
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
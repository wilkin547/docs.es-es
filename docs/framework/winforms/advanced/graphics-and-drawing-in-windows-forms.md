---
title: "Gr&#225;ficos y dibujos en Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "dibujar [formularios Windows Forms]"
  - "GDI+, con código administrado"
  - "gráficos [formularios Windows Forms]"
  - "gráficos, usar en Windows Forms"
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gr&#225;ficos y dibujos en Windows Forms
Common Language Runtime usa una implementación avanzada de la interfaz de dispositivo gráfico de Windows \([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\) llamada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] está diseñada para proporcionar rendimiento y facilidad de uso.  Puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar imágenes gráficas en Windows Forms y en controles.  Aunque no puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control Image de servidor web.  
  
 En esta sección, encontrará temas que presentan los conceptos básicos de la programación de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes.  Para obtener más información, consulte el tema «Referencia de GDI\+» en MSDN Library en http:\/\/msdn.microsoft.com\/library.  
  
## En esta sección  
 [Información general de gráficos](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 Proporciona una introducción a las clases administradas relacionadas con gráficos.  
  
 [Código administrado de GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 Proporciona información acerca de las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 Muestra cómo completar diferentes tareas usando las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## Referencia  
 <xref:System.Drawing>  
 Proporciona acceso a la funcionalidad básica de gráficos de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Drawing2D>  
 Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.  
  
 <xref:System.Drawing.Imaging>  
 Proporciona la funcionalidad avanzada de imágenes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Text>  
 Proporciona la funcionalidad avanzada de tipografía de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.  
  
 <xref:System.Drawing.Printing>  
 Proporciona la funcionalidad de impresión.  
  
## Secciones relacionadas  
 [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 Detalla cómo proporcionar código para dibujar controles.
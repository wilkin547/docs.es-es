---
title: "Tres categor&#237;as de servicios gr&#225;ficos | Microsoft Docs"
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
  - "gráficos vectoriales 2D"
  - "gráficos, categorías"
  - "imágenes"
  - "tipografía"
  - "gráficos vectoriales"
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Tres categor&#237;as de servicios gr&#225;ficos
Las sugerencias de los gráficos en formularios Windows Forms pertenecen a las tres categorías siguientes:  
  
-   Gráficos vectoriales bidimensionales \(2D\)  
  
-   Imágenes  
  
-   Tipografía  
  
## Gráficos vectoriales 2D  
 Gráficos vectoriales que están relacionados con el dibujo de tipos primitivos \(como líneas, curvas y figuras\) y que se especifican mediante conjuntos de puntos en un sistema de coordenadas.  Por ejemplo, una línea recta puede especificarse mediante sus dos extremos, y un rectángulo puede especificarse mediante un punto que indique la ubicación del borde superior izquierdo y un par de números que indiquen el ancho y el alto.  Un trazado simple puede especificarse mediante una matriz de puntos que se van a conectar mediante líneas rectas.  Una curva spline de Bézier es una curva sofisticada especificada por cuatro puntos de control.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona clases y estructuras que almacenan información acerca de los propios tipos primitivos, las clases que almacenan información sobre la forma en que deben dibujarse los tipos primitivos y las clases que realmente realizan el dibujo.  Por ejemplo, la estructura <xref:System.Drawing.Rectangle> almacena la ubicación y el tamaño de un rectángulo; la clase <xref:System.Drawing.Pen> almacena información sobre el color de línea, ancho de línea y estilo de línea; y la clase <xref:System.Drawing.Graphics> dispone de métodos para dibujar líneas, rectángulos, trazados y otras figuras.  También existen varias clases <xref:System.Drawing.Brush> que almacenan información sobre la forma en que las figuras cerradas y los trazados van a rellenarse con colores o modelos.  
  
 Puede registrar en un metarchivo una imagen de vector que sea una secuencia de comandos gráficos.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona la clase <xref:System.Drawing.Imaging.Metafile> para registrar, mostrar y guardar metarchivos.  Con las clases <xref:System.Drawing.Imaging.MetafileHeader> y <xref:System.Drawing.Imaging.MetaHeader> puede inspeccionar los datos almacenados en un encabezado de metarchivo.  
  
## Imágenes  
 Hay ciertos tipos de imágenes que no se pueden o son muy difíciles de mostrar con las técnicas de gráficos vectoriales.  Por ejemplo, las imágenes de los botones de la barra de herramientas y las imágenes que aparecen en forma de iconos serían difíciles de especificar en forma de colecciones de líneas y curvas.  Una fotografía digital de alta resolución de un estadio de béisbol abarrotado sería aún más difícil de crear con las técnicas vectoriales.  Este tipo de imágenes se almacena en mapas de bits, que son matrices de números que representan colores de puntos individuales en la pantalla.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona la clase <xref:System.Drawing.Bitmap> para mostrar, manipular y guardar mapas de bits.  
  
## Tipografía  
 La tipografía es la presentación de texto en una variedad de fuentes, tamaños y estilos.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona una extensa compatibilidad para esta compleja tarea.  Una de las nuevas características de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es la función de suavizado de contorno de subpíxel, que proporciona una apariencia más regular al texto que se representa en una pantalla LCD.  
  
 Además, Windows Forms ofrece la opción de dibujar texto con funciones [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] en su clase <xref:System.Windows.Forms.TextRenderer>.  
  
## Vea también  
 [Información general de gráficos](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [Código administrado de GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [Utilizar clases gráficas administradas](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
---
title: Tres categorías de servicios gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525052"
---
# <a name="three-categories-of-graphics-services"></a>Tres categorías de servicios gráficos
Las ofertas de gráficos en formularios Windows Forms se dividen en tres amplias categorías:  
  
-   Gráficos vectoriales bidimensionales (2D)  
  
-   Creación de imágenes  
  
-   Tipografía  
  
## <a name="2-d-vector-graphics"></a>Gráficos vectoriales 2D  
 Gráficos vectoriales bidimensionales son primitivos; Por ejemplo, las líneas, curvas y figuras; que se especifican los conjuntos de puntos en un sistema de coordenadas. Por ejemplo, una línea recta se especifica mediante sus dos extremos, y un rectángulo especificado por un punto que indique la ubicación de la esquina superior izquierda y un par de números que indiquen su ancho y alto. Se especifica una ruta de acceso simple por una matriz de puntos conectados por líneas rectas. Una curva spline de Bézier es una curva sofisticada especificada por cuatro puntos de control.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Proporciona clases y estructuras que almacenan información acerca de los tipos primitivos por sí mismos, las clases que almacenan información sobre cómo se extraen los tipos primitivos y las clases que realmente realizan el dibujo. Por ejemplo, el <xref:System.Drawing.Rectangle> estructura almacena la ubicación y el tamaño de un rectángulo; la <xref:System.Drawing.Pen> clase almacena información sobre el color de línea, el ancho de línea y el estilo de línea; y la <xref:System.Drawing.Graphics> clase tiene métodos para dibujar líneas, rectángulos, las rutas de acceso, y otras figuras. Hay también varios <xref:System.Drawing.Brush> las clases que almacenan información acerca de cómo cerrar las cifras y las rutas de acceso se rellena con colores o patrones.  
  
 Puede registrar una imagen de vector, que es una secuencia de comandos de gráficos, en un metarchivo. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona la <xref:System.Drawing.Imaging.Metafile> clase para registrar, mostrar y guardar metarchivos. Con el <xref:System.Drawing.Imaging.MetafileHeader> y <xref:System.Drawing.Imaging.MetaHeader> clases, puede inspeccionar los datos almacenados en un encabezado de metarchivo.  
  
## <a name="imaging"></a>Creación de imágenes  
 Ciertos tipos de imágenes sean difíciles o imposibles mostrar con las técnicas de gráficos vectoriales. Por ejemplo, las imágenes de botones de barra de herramientas y las imágenes que aparecen como iconos son difíciles de especificar que las colecciones de líneas y curvas conectadas. Una fotografía digital de alta resolución de un estadio de béisbol abarrotado es incluso más difícil de crear con las técnicas vectoriales. Imágenes de este tipo se almacenan como mapas de bits, que son matrices de números que representan los colores de puntos individuales en la pantalla. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona la <xref:System.Drawing.Bitmap> clase para mostrar, manipular y guardar mapas de bits.  
  
## <a name="typography"></a>Tipografía  
 Tipografía es la presentación del texto en una variedad de fuentes, tamaños y estilos. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Proporciona una amplia compatibilidad para esta tarea compleja. Una de las nuevas características de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] se suavizado de contorno de subpíxel, que proporciona texto que se representa en una pantalla LCD una apariencia más suave.  
  
 Además, Windows Forms ofrece la opción de dibujar texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capacidades en su <xref:System.Windows.Forms.TextRenderer> clase.  
  
## <a name="see-also"></a>Vea también  
 [Graphics Overview](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])  
 [About GDI+ Managed Code](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
 [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)

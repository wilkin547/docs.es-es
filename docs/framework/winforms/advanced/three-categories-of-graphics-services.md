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
ms.openlocfilehash: ccbd5e236b47d1d870c9b77cfa2b3880619cf3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651524"
---
# <a name="three-categories-of-graphics-services"></a>Tres categorías de servicios gráficos
Las ofertas de gráficos en Windows Forms se dividen en tres amplias categorías:  
  
- Gráficos vectoriales bidimensionales (2D)  
  
- Creación de imágenes  
  
- Tipografía  
  
## <a name="2-d-vector-graphics"></a>Gráficos vectoriales 2D  
 Gráficos vectoriales bidimensionales son primitivos; Por ejemplo, líneas, curvas y cifras; que se especifican mediante conjuntos de puntos en un sistema de coordenadas. Por ejemplo, se especifica una línea recta mediante sus dos extremos, y un rectángulo especificado por un punto de la ubicación de la esquina superior izquierda y un par de números que indiquen su ancho y alto. Se especifica una ruta de acceso simple mediante una matriz de puntos que están conectados mediante líneas rectas. Una curva spline de Bézier es una curva sofisticada especificada por cuatro puntos de control.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Proporciona clases y estructuras que almacenan información sobre los tipos primitivos a sí mismos, las clases que almacenan información sobre cómo se va a dibujar los tipos primitivos y las clases que realmente realizan el dibujo. Por ejemplo, el <xref:System.Drawing.Rectangle> estructura almacena la ubicación y tamaño de un rectángulo; el <xref:System.Drawing.Pen> clase almacena información sobre el color de línea, ancho de línea y estilo de línea; y la <xref:System.Drawing.Graphics> clase tiene métodos para dibujar líneas, rectángulos, las rutas de acceso, y otras cifras. Hay también varios <xref:System.Drawing.Brush> las clases que almacenan información acerca de cómo cerrar las cifras y rutas de acceso se rellenará con los patrones o colores.  
  
 Puede grabar una imagen de vector, que es una secuencia de comandos gráficos, en un metarchivo. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona el <xref:System.Drawing.Imaging.Metafile> clase para registrar, mostrar y guardar metarchivos. Con el <xref:System.Drawing.Imaging.MetafileHeader> y <xref:System.Drawing.Imaging.MetaHeader> clases, puede inspeccionar los datos almacenados en un encabezado de metarchivo.  
  
## <a name="imaging"></a>Creación de imágenes  
 Ciertos tipos de imágenes son difíciles o imposibles de mostrar con las técnicas de gráficos vectoriales. Por ejemplo, las imágenes de los botones de barra de herramientas y las imágenes que aparecen como iconos son difíciles de especificar como colecciones de líneas y curvas. Una fotografía digital de alta resolución de un estadio de béisbol abarrotado es incluso más difícil de crear con las técnicas de vector. Imágenes de este tipo se almacenan como mapas de bits, que son matrices de números que representan los colores de puntos individuales en la pantalla. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona el <xref:System.Drawing.Bitmap> clase para mostrar, manipular y guardar mapas de bits.  
  
## <a name="typography"></a>Tipografía  
 Tipografía es la presentación del texto en una variedad de fuentes, tamaños y estilos. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Proporciona una amplia compatibilidad para esta tarea compleja. Una de las nuevas características de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es suavizado de contorno de subpíxeles, lo que proporciona el texto representado en una pantalla LCD una apariencia más suave.  
  
 Además, Windows Forms ofrece la opción de dibujar texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capacidades en su <xref:System.Windows.Forms.TextRenderer> clase.  
  
## <a name="see-also"></a>Vea también

- [Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])
- [About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)
- [Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)

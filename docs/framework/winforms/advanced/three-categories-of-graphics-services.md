---
title: Tres categorías de servicios gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: b0f2ad8293daf6ad53899a0f8be82985c24ff50d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111210"
---
# <a name="three-categories-of-graphics-services"></a>Tres categorías de servicios gráficos
Las ofertas de gráficos en Formularios Windows Forms se dividen en las siguientes tres categorías generales:  
  
- Gráficos vectoriales bidimensionales (2-D)  
  
- Creación de imágenes  
  
- Tipografía  
  
## <a name="2d-vector-graphics"></a>Gráficos vectoriales 2D  
 Los gráficos vectoriales bidimensionales son primitivos; como líneas, curvas y figuras; que se especifican mediante conjuntos de puntos en un sistema de coordenadas. Por ejemplo, una línea recta se especifica mediante sus dos extremos y un rectángulo se especifica mediante un punto que indica la ubicación de su esquina superior izquierda y un par de números que dan su ancho y alto. Una ruta simple se especifica mediante una matriz de puntos que están conectados por líneas rectas. Una spline de Bézier es una curva sofisticada especificada por cuatro puntos de control.  
  
 GDI+GDI+GDI+ proporciona clases y estructuras que almacenan información sobre los propios primitivos, clases que almacenan información sobre cómo se dibujarán los primitivos y clases que realmente realizan el dibujo. Por ejemplo, <xref:System.Drawing.Rectangle> la estructura almacena la ubicación y el tamaño de un rectángulo; la <xref:System.Drawing.Pen> clase almacena información sobre el color de línea, el ancho de línea y el estilo de línea; y <xref:System.Drawing.Graphics> la clase tiene métodos para dibujar líneas, rectángulos, trazados y otras figuras. También hay <xref:System.Drawing.Brush> varias clases que almacenan información sobre cómo las figuras cerradas y los trazados se llenarán de colores o patrones.  
  
 Puede grabar una imagen vectorial, que es una secuencia de comandos gráficos, en un metarchivo. GDI+GDI+ proporciona la <xref:System.Drawing.Imaging.Metafile> clase para grabar, mostrar y guardar metarchivos. Con <xref:System.Drawing.Imaging.MetafileHeader> las <xref:System.Drawing.Imaging.MetaHeader> clases y, puede inspeccionar los datos almacenados en un encabezado de metarchivo.  
  
## <a name="imaging"></a>Creación de imágenes  
 Ciertos tipos de imágenes son difíciles o imposibles de mostrar con las técnicas de gráficos vectoriales. Por ejemplo, las imágenes de los botones de la barra de herramientas y las imágenes que aparecen como iconos son difíciles de especificar como colecciones de líneas y curvas. Una fotografía digital de alta resolución de un estadio de béisbol lleno de gente es aún más difícil de crear con técnicas vectoriales. Las imágenes de este tipo se almacenan como mapas de bits, que son matrices de números que representan los colores de puntos individuales en la pantalla. GDI+GDI+GDI+ proporciona la <xref:System.Drawing.Bitmap> clase para mostrar, manipular y guardar mapas de bits.  
  
## <a name="typography"></a>Tipografía  
 La tipografía es la visualización del texto en una variedad de fuentes, tamaños y estilos. GDI+GDI+ proporciona un amplio soporte para esta compleja tarea. Una de las nuevas características de GDI+ es el antialiasing de subpíxeles, que proporciona un aspecto más suave al texto renderizado en una pantalla LCD.  
  
 Además, Windows Forms ofrece la opción de <xref:System.Windows.Forms.TextRenderer> dibujar texto con capacidades GDI en su clase.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre gráficos](graphics-overview-windows-forms.md)
- [Código administrado de GDI+](about-gdi-managed-code.md)
- [Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)

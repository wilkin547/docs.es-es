---
title: Gráficos y dibujo
description: Obtenga información sobre los objetos Graphics, Pen, Brush y color, y cómo realizar tareas como dibujar formas, dibujar texto o mostrar imágenes en Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618407"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Gráficos y dibujos en Windows Forms
En el Common Language Runtime se usa una implementación avanzada de Windows Interfaz de dispositivo gráfico (GDI) denominada GDI+. Con GDI+ puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos. GDI+ está diseñado para ofrecer rendimiento y facilidad de uso. Puede usar GDI+ para representar imágenes gráficas en Windows Forms y controles. Aunque no puede usar GDI+ directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control imagen de servidor Web.  
  
 En esta sección, encontrará temas que presentan los aspectos básicos de la programación con GDI+. Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes. Para obtener más información, vea [referencia de GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md). Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre gráficos](graphics-overview-windows-forms.md)  
 Proporciona una introducción a las clases administradas relacionadas con gráficos.  
  
 [Código administrado de GDI+](about-gdi-managed-code.md)  
 Proporciona información sobre las clases administradas de GDI+.  
  
 [Utilizar clases gráficas administradas](using-managed-graphics-classes.md)  
 Muestra cómo realizar una serie de tareas mediante las clases administradas de GDI+.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing>  
 Proporciona acceso a la funcionalidad de gráficos básica de GDI+.  
  
 <xref:System.Drawing.Drawing2D>  
 Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.  
  
 <xref:System.Drawing.Imaging>  
 Proporciona funcionalidad avanzada de imágenes de GDI+.  
  
 <xref:System.Drawing.Text>  
 Proporciona funcionalidad avanzada de tipografía de GDI+. Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.  
  
 <xref:System.Drawing.Printing>  
 Proporciona la funcionalidad de impresión.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Dibujo y representación personalizados de controles](../controls/custom-control-painting-and-rendering.md)  
 Detalla cómo proporcionar código para dibujar controles.

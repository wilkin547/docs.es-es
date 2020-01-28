---
title: Gráficos y dibujo
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746405"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Gráficos y dibujos en Windows Forms
En el Common Language Runtime se usa una implementación avanzada de Windows Interfaz de dispositivo gráfico (GDI) denominada GDI+. Con GDI+ puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos. GDI+ está diseñado para ofrecer rendimiento y facilidad de uso. Puede usar GDI+ para representar imágenes gráficas en Windows Forms y controles. Aunque no puede usar GDI+ directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control imagen de servidor Web.  
  
 En esta sección, encontrará temas que presentan los aspectos básicos de la programación con GDI+. Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes. Para obtener más información, vea [referencia de GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md). Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.  
  
## <a name="in-this-section"></a>Esta sección  
 [Información general de gráficos](graphics-overview-windows-forms.md)  
 Proporciona una introducción a las clases administradas relacionadas con gráficos.  
  
 [About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
 Proporciona información sobre las clases administradas de GDI+.  
  
 [Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)  
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
 [Custom Control Painting and Rendering](../controls/custom-control-painting-and-rendering.md) (Pintura y representación personalizadas de controles)  
 Detalla cómo proporcionar código para dibujar controles.

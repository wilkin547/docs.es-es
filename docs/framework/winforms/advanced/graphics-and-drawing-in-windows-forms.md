---
title: Gráficos y dibujos en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505544"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Gráficos y dibujos en Windows Forms
Common language runtime usa una implementación avanzada de la interfaz de dispositivo de gráficos de Windows (GDI) denominada GDI +. Con GDI + puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos. GDI + está diseñado para ofrecer rendimiento y facilidad de uso. Puede usar GDI + para representar imágenes gráficas en Windows Forms y controles. Aunque no se puede utilizar GDI + directamente en los formularios Web Forms, puede mostrar imágenes gráficas mediante el control Image de servidor Web.  
  
 En esta sección, encontrará temas que presentan los conceptos básicos de programación de GDI +. Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes. Para obtener más información, consulte [referencia de GDI +](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md). Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.  
  
## <a name="in-this-section"></a>En esta sección  
 [Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])  
 Proporciona una introducción a las clases administradas relacionadas con gráficos.  
  
 [About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
 Proporciona información sobre las clases administradas de GDI +.  
  
 [Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)  
 Muestra cómo para completar una serie de tareas con GDI + clases administradas.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing>  
 Proporciona acceso a la funcionalidad básica de gráficos GDI +.  
  
 <xref:System.Drawing.Drawing2D>  
 Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.  
  
 <xref:System.Drawing.Imaging>  
 Proporciona funciones de imagen avanzadas para GDI +.  
  
 <xref:System.Drawing.Text>  
 Proporciona funciones de tipografía avanzadas para GDI +. Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.  
  
 <xref:System.Drawing.Printing>  
 Proporciona la funcionalidad de impresión.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Custom Control Painting and Rendering](../controls/custom-control-painting-and-rendering.md) (Pintura y representación personalizadas de controles)  
 Detalla cómo proporcionar código para dibujar controles.

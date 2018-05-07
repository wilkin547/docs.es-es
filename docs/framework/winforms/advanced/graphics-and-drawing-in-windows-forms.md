---
title: Gráficos y dibujos en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 3dbb5d36ce2e550c0420a23b40247771e10d60ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Gráficos y dibujos en Windows Forms
Common Language Runtime usa una implementación avanzada de la interfaz de dispositivo gráfico de Windows ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) llamada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede crear gráficos, dibujar texto y manipular imágenes gráficas como objetos. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] está diseñada para proporcionar rendimiento y facilidad de uso. Puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar imágenes gráficas en Windows Forms y en controles. Aunque no puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directamente en formularios Web Forms, puede mostrar imágenes gráficas mediante el control Image de servidor web.  
  
 En esta sección, encontrará temas que presentan los conceptos básicos de la programación de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Aunque no pretende ser una referencia exhaustiva, esta sección incluye información sobre los objetos <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> y <xref:System.Drawing.Color>, y explica cómo realizar tareas tales como dibujar formas, dibujar texto o mostrar imágenes. Para obtener más información, consulte [referencia de GDI +](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).  
  
 Si quiere incorporarse y empezar a trabajar inmediatamente, vea [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md). Encontrará temas sobre cómo usar código para dibujar líneas, formas, texto y mucho más en Windows Forms.  
  
## <a name="in-this-section"></a>En esta sección  
 [Graphics Overview](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])  
 Proporciona una introducción a las clases administradas relacionadas con gráficos.  
  
 [About GDI+ Managed Code](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
 Proporciona información acerca de las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)  
 Muestra cómo completar diferentes tareas usando las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing>  
 Proporciona acceso a la funcionalidad básica de gráficos de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Drawing2D>  
 Proporciona funcionalidad avanzada de gráficos vectoriales y bidimensionales.  
  
 <xref:System.Drawing.Imaging>  
 Proporciona la funcionalidad avanzada de imágenes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Text>  
 Proporciona la funcionalidad avanzada de tipografía de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Las clases de este espacio de nombres se pueden usar para crear y utilizar colecciones de fuentes.  
  
 <xref:System.Drawing.Printing>  
 Proporciona la funcionalidad de impresión.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md) (Pintura y representación personalizadas de controles)  
 Detalla cómo proporcionar código para dibujar controles.

---
title: "C&#243;mo: Dibujar l&#237;neas con el control LineShape (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "líneas, dibujar"
  - "LineShape (control)"
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Dibujar l&#237;neas con el control LineShape (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede utilizar el control <xref:Microsoft.VisualBasic.PowerPacks.LineShape> para dibujar líneas horizontales, verticales o diagonales en un formulario o contenedor, tanto en tiempo de diseño como en tiempo de ejecución.  
  
 **Nota**: es posible que su equipo muestre nombres o ubicaciones diferentes para algunos de los elementos de la interfaz de usuario de Visual Studio en las siguientes instrucciones.  La edición de Visual Studio que tenga y la configuración que esté usando determinan estos elementos.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para dibujar una línea en tiempo de diseño  
  
1.  Arrastre el control <xref:Microsoft.VisualBasic.PowerPacks.LineShape> desde la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** hasta un control de formulario o un control contenedor.  
  
2.  Arrastre los controladores de tamaño y desplazamiento para ajustar el tamaño de la línea y colocarla.  
  
     También puede ajustar el tamaño de la línea y colocarla cambiando las propiedades `X1`, `X2`, `Y2` y `Y1` en la ventana **Propiedades**.  
  
3.  En la ventana **Propiedades**, establezca opcionalmente propiedades adicionales como `BorderStyle` o `BorderColor` para cambiar la apariencia de la línea.  
  
### Para dibujar una línea en tiempo de ejecución  
  
1.  Haga clic en la opción **Agregar referencia** del menú **Proyecto**.  
  
2.  En el cuadro de diálogo **Agregar referencia**, seleccione **Microsoft.VisualBasic.PowerPacks.VS** y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **Editor de código**, agregue una instrucción `Imports` o `using` al comienzo del módulo:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  Agregue el código siguiente a un procedimiento de `Event`:  
  
     [!code-cs[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>   
 [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
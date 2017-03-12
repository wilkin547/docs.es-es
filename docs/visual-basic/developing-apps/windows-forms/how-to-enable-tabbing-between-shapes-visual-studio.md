---
title: "C&#243;mo: Habilitar la tabulaci&#243;n entre las formas (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line (control), implementar la tabulación"
  - "Shape (control), implementar la tabulación"
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Habilitar la tabulaci&#243;n entre las formas (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los controles de líneas y formas no tienen propiedades `TabIndex` sino `TabStop`, pero todavía puede habilitar la tabulación entre ellos.  En el ejemplo siguiente, presionando las teclas CTRL y TAB, se tabulará entre las formas; presionando sólo la tecla TAB, se tabulará entre los botones.  
  
> [!NOTE]
>  Es posible que su equipo muestre nombres o ubicaciones diferentes para algunos de los elementos de la interfaz de usuario de Visual Studio en las siguientes instrucciones.  La edición de Visual Studio que tenga y la configuración que esté usando determinan estos elementos.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para habilitar la tabulación entre las formas  
  
1.  Arrastre tres controles <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> y dos controles <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** a un formulario.  
  
2.  En el **Editor de código**, agregue una instrucción `Imports` o `using` al comienzo del módulo:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
3.  Agregue el código siguiente a un procedimiento de evento:  
  
     [!code-cs[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksTabbingCS/VbPowerPacksTabbing.cs#1)]
     [!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksTabbing/VbPowerPacksTabbing.vb#1)]  
  
4.  Agregue el código siguiente al procedimiento de evento `Button1_PreviewKeyDown`:  
  
     [!code-cs[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksTabbingCS/VbPowerPacksTabbing.cs#2)]
     [!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksTabbing/VbPowerPacksTabbing.vb#2)]  
  
## Vea también  
 [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [Cómo: Dibujar líneas con el control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
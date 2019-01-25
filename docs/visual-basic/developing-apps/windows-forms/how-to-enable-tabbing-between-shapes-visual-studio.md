---
title: Procedimiento Habilitar la tabulación entre las formas (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
ms.openlocfilehash: c47d94317008af57907b747e53bd13ae7ca229f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498286"
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>Procedimiento Habilitar la tabulación entre las formas (Visual Studio)
No tiene controles Line y shape `TabStop` o `TabIndex` las propiedades, pero se puede habilitar la tabulación entre ellos. En el ejemplo siguiente, se presiona la tecla CTRL y las teclas TAB pestaña entre formas; solo la tecla TAB se tab para pasar de los botones.  
  
> [!NOTE]
>  Es posible que el equipo muestre nombres o ubicaciones diferentes para algunos de los elementos de la interfaz de usuario de Visual Studio en las siguientes instrucciones. La edición de Visual Studio que se tenga y la configuración que se utilice determinan estos elementos. Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="to-enable-tabbing-among-shapes"></a>Para habilitar la tabulación entre las formas  
  
1.  Arrastre tres <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controles y dos <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** a un formulario.  
  
2.  En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  Agregue el código siguiente en un procedimiento de evento:  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Agregue el código siguiente en el `Button1_PreviewKeyDown` procedimiento de evento:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Vea también
- [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Cómo: Dibujar líneas con el Control LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)

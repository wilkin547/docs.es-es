---
title: Procedimiento Dibujar líneas con el Control LineShape (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596233"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Procedimiento Dibujar líneas con el Control LineShape (Visual Studio)
Puede usar el <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control para dibujar líneas horizontales, verticales o diagonales en un formulario o contenedor, tanto en tiempo de diseño y en tiempo de ejecución.  
  
 **Tenga en cuenta** su equipo podría muestre nombres o ubicaciones para algunos de los usuarios de Visual Studio diferentes elementos de la interfaz en las instrucciones siguientes. La edición de Visual Studio que se tenga y la configuración que se utilice determinan estos elementos. Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-line-at-design-time"></a>Para dibujar una línea en tiempo de diseño  
  
1.  Arrastre el <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** arrastrar a un control de formulario o contenedor.  
  
2.  Arrastre el ajuste de tamaño y mover los controladores de tamaño y posición de la línea.  
  
     También puede cambiar el tamaño y la posición de la línea cambiando el `X1`, `X2`, `Y1`, y `Y2` propiedades en el **propiedades** ventana.  
  
3.  En el **propiedades** ventana, opcionalmente, establecer propiedades adicionales, como `BorderStyle` o `BorderColor` para cambiar la apariencia de la línea.  
  
### <a name="to-draw-a-line-at-run-time"></a>Para dibujar una línea en tiempo de ejecución  
  
1.  En el menú **Proyecto**, haga clic en **Agregar referencia**.  
  
2.  En el **Agregar referencia** cuadro de diálogo, seleccione **Microsoft.VisualBasic.PowerPacks.VS**y, a continuación, haga clic en **Aceptar**.  
  
3.  En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Agregue el código siguiente en un procedimiento `Event`:  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [Introducción a los controles de líneas y formas](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [Cómo: Dibujar formas con los controles OvalShape y RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)

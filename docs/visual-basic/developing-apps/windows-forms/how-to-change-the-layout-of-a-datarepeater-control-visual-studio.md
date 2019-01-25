---
title: Procedimiento Cambiar el diseño de un Control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625606"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Procedimiento Cambiar el diseño de un Control DataRepeater (Visual Studio)
El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control puede mostrarse en una vertical (elementos de desplazamiento vertical) o en horizontal (elementos de desplazamiento horizontal) orientación. Puede cambiar la orientación en tiempo de diseño o en tiempo de ejecución, cambie el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad. Si cambia el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad en tiempo de ejecución, también puede cambiar el tamaño de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y la posición de los controles secundarios.  
  
> [!NOTE]
>  Si cambia la posición de los controles en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en tiempo de ejecución, deberá llamar a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> métodos al principio y al final del bloque de código que cambia de posición los controles.  
  
### <a name="to-change-the-layout-at-design-time"></a>Para cambiar el diseño en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
    > [!NOTE]
    >  Debe seleccionar el borde exterior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control haciendo clic en la región inferior del control, no en la esquina superior <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> región.  
  
2.  En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad como <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>Para cambiar el diseño en tiempo de ejecución  
  
1.  Agregue el código siguiente a un botón o menú `Click` controlador de eventos:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  En la mayoría de los casos, desea agregar código similar al que se muestra en la sección ejemplo para cambiar el tamaño de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y reorganizar los controles para ajustarse a la nueva orientación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo responder a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> eventos en un controlador de eventos. En este ejemplo requiere que haya un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control denominado `DataRepeater1` en un formulario y que su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contienen dos <xref:System.Windows.Forms.TextBox> controles denominados `TextBox1` y `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Cómo: Cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)

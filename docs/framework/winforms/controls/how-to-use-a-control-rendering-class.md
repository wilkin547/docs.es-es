---
title: Filtrar Usar una clase de representación de controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: d9da43b1686f416cf2149cef07665b0a726c3b0c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723158"
---
# <a name="how-to-use-a-control-rendering-class"></a>Filtrar Usar una clase de representación de controles
Este ejemplo muestra cómo usar el <xref:System.Windows.Forms.ComboBoxRenderer> clase para representar la flecha de lista desplegable de una combinación de control de cuadro. El ejemplo consta de los <xref:System.Windows.Forms.Control.OnPaint%2A> método de un control personalizado simple. El <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> propiedad se utiliza para determinar si los estilos visuales están habilitados en el área de cliente de windows de la aplicación. Si los estilos visuales están activos, el <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> método representará la flecha de lista desplegable con estilos visuales; de lo contrario, el <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> método representará la flecha desplegable en el estilo clásico de Windows.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control personalizado derivado de la <xref:System.Windows.Forms.Control> clase.  
  
-   Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.  
  
-   Las referencias a la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, y <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> espacios de nombres.  
  
## <a name="see-also"></a>Vea también
- [Representar controles con estilos visuales](rendering-controls-with-visual-styles.md)

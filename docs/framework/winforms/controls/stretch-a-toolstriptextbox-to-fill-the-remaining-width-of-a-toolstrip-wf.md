---
title: 'Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742843"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms)
Cuando se establece la propiedad <xref:System.Windows.Forms.ToolStrip.Stretch%2A> de un control <xref:System.Windows.Forms.ToolStrip> en `true`, el control rellena su contenedor de un extremo a otro y cambia de tamaño cuando se cambia el tamaño de su contenedor. En esta configuración, puede que le resulte útil expandir un elemento del control, como un <xref:System.Windows.Forms.ToolStripTextBox>, para rellenar el espacio disponible y cambiar el tamaño cuando el control cambia de tamaño. Esta ampliación es útil, por ejemplo, si desea lograr la apariencia y el comportamiento similares a la barra de direcciones de Microsoft® Internet Explorer.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> denominada `ToolStripSpringTextBox`. Esta clase invalida el método <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> para calcular el ancho disponible del control primario <xref:System.Windows.Forms.ToolStrip> una vez que se ha restado el ancho combinado de todos los demás elementos. En este ejemplo de código también se proporciona una clase <xref:System.Windows.Forms.Form> y una clase `Program` para mostrar el nuevo comportamiento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Utilizar la propiedad Spring de manera interactiva en un control StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

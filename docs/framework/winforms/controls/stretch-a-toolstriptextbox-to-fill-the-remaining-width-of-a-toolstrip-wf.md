---
title: 'Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537725"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Cómo: Ajustar un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (Windows Forms)
Al establecer el <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propiedad de un <xref:System.Windows.Forms.ToolStrip> el control a `true`, el control rellena su contenedor de extremo a extremo y cambian de tamaño cuando cambia el tamaño de su contenedor. En esta configuración, quizá le resulte útil para ajustar un elemento en el control, como un <xref:System.Windows.Forms.ToolStripTextBox>, para rellenar el espacio disponible y cambian de tamaño cuando el control cambia de tamaño. Este ajuste es útil, por ejemplo, si desea obtener una apariencia y comportamiento similar a la barra de direcciones de Microsoft® Internet Explorer.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> denominado `ToolStripSpringTextBox`. Esta clase reemplaza la <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> método para calcular el ancho disponible del elemento primario <xref:System.Windows.Forms.ToolStrip> controlar una vez se ha restado el ancho combinado de todos los demás elementos. Este ejemplo de código también proporciona un <xref:System.Windows.Forms.Form> clase y un `Program` clase para mostrar el nuevo comportamiento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Utilizar la propiedad Spring de manera interactiva en un control StatusStrip](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

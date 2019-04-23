---
title: Procedimiento Un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 707fd2e470a9be1d61d2878eeff845b3cad270db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223581"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Procedimiento Un elemento ToolStripTextBox para llenar el ancho restante de un control ToolStrip (formularios Windows Forms)
Al establecer el <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propiedad de un <xref:System.Windows.Forms.ToolStrip> el control a `true`, el control rellena su contenedor de extremo a extremo y cambia de tamaño cuando cambia el tamaño de su contenedor. En esta configuración, le resultará útil para ajustar un elemento en el control, como un <xref:System.Windows.Forms.ToolStripTextBox>, para rellenar el espacio disponible y para cambiar el tamaño cuando el control cambia de tamaño. Este ajuste es útil, por ejemplo, si desea obtener una apariencia y comportamiento similar a la barra de direcciones en Microsoft® Internet Explorer.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se proporciona una clase derivada de <xref:System.Windows.Forms.ToolStripTextBox> llamado `ToolStripSpringTextBox`. Esta clase invalida el <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> método para calcular el ancho disponible del elemento primario <xref:System.Windows.Forms.ToolStrip> controlar una vez restado el ancho combinado de todos los demás elementos. Este ejemplo de código también proporciona un <xref:System.Windows.Forms.Form> clase y un `Program` clase para mostrar el nuevo comportamiento.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

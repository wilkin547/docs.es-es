---
title: 'Cómo: Disponer objetos en capas en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 1a2a25f2e7eaa6618c0bf535a34f7dc6a28d51fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533691"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Cómo: Disponer objetos en capas en formularios Windows Forms
Al crear una interfaz de usuario complejas o trabajar con un formulario de múltiples documentos (MDI) de la interfaz, que a menudo desea capas controles y formularios secundarios para crear interfaces de usuario (UI) más complejas. Para mover y realizar un seguimiento de los controles y ventanas en el contexto de un grupo, manipular su orden z. *Orden Z* constituye las capas visuales de controles en un formulario de eje z del formulario (profundidad). La ventana en la parte superior del orden z superpone a todas las demás ventanas. Todas las demás ventanas superponen a la ventana en la parte inferior del orden z.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-layer-controls-at-design-time"></a>Para superponer los controles en tiempo de diseño  
  
1.  Seleccione un control que desee disponer en capas.  
  
2.  En el **formato** menú, elija **orden**y, a continuación, haga clic en **Traer al frente** o **hacia atrás**.  
  
### <a name="to-layer-controls-programmatically"></a>Disponer en capas los controles mediante programación  
  
-   Use la <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> métodos para manipular el orden z de los controles.  
  
     Por ejemplo, si un <xref:System.Windows.Forms.TextBox> control `txtFirstName`, está debajo de la directiva otro control y desea tener en la parte superior, utilice el código siguiente:  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Formularios Windows Forms admiten *contención de controles*. Contención de controles permite colocar una serie de controles dentro de un control contenedor, como un número de <xref:System.Windows.Forms.RadioButton> controla dentro de un <xref:System.Windows.Forms.GroupBox> control. A continuación, puede crear niveles en los controles en el control contenedor. Mover el cuadro de grupo mueve a los controles, porque están contenidos dentro de él.  
  
## <a name="see-also"></a>Vea también  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

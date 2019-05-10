---
title: Procedimiento para disponer objetos en capas en formularios Windows Forms
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
ms.openlocfilehash: 6000adeffcc991557e046461f93fec24e1262f54
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651685"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Procedimiento para disponer objetos en capas en formularios Windows Forms
Al crear una interfaz de usuario complejas o trabajar con un formulario de múltiples documentos (MDI) de la interfaz, que a menudo desea capas controles y formularios secundarios para crear interfaces de usuario (UI) más complejas. Para mover y realizar un seguimiento de los controles y ventanas dentro del contexto de un grupo, manipular su orden z. *Orden Z* es el diseño visual de los controles en un formulario de eje z del formulario (intensidad). La ventana en la parte superior del orden z se superpone a todas las demás ventanas. Todas las demás ventanas superponen a la ventana en la parte inferior del orden z.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-layer-controls-at-design-time"></a>Para superponer los controles en tiempo de diseño  
  
1. Seleccione un control que desee en capas.  
  
2. En el **formato** menú, elija **orden**y, a continuación, haga clic en **Traer al frente** o **enviar al fondo**.  
  
### <a name="to-layer-controls-programmatically"></a>En capas los controles mediante programación  
  
- Use la <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> métodos para manipular el orden z de los controles.  
  
     Por ejemplo, si un <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, está debajo de la directiva otro control y desea que en la parte superior, use el siguiente código:  
  
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
>  Los formularios Windows Forms admiten *contención de controles*. Contención de controles implica la colocación de una serie de controles dentro de un control contenedor, como un número de <xref:System.Windows.Forms.RadioButton> controla dentro de un <xref:System.Windows.Forms.GroupBox> control. A continuación, puede agregar los controles dentro del control contenedor. Mover el grupo mueve los controles, porque están contenidos dentro de él.  
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms](index.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)

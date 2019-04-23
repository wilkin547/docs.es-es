---
title: Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: f127a1a74643c975aea73b24896c098b365aa327
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327547"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador
En cualquier formulario de Windows, se puede designar un <xref:System.Windows.Forms.Button> que sea el botón Cancelar del control. Cada vez que el usuario presiona la tecla ESC, independientemente de que otro control en el formulario tiene el foco, se hace clic en un botón Cancelar. Habitualmente se programa un botón para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-designate-the-cancel-button"></a>Para designar el botón Cancelar  
  
1. Seleccione el formulario en el que reside el botón.  
  
2. En el **propiedades** ventana, establezca el formulario <xref:System.Windows.Forms.Form.CancelButton%2A> propiedad a la <xref:System.Windows.Forms.Button> nombre del control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)

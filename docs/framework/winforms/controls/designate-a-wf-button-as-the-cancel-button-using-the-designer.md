---
title: "Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e1667d086f26759e0129fc62d94ea79c68d880
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador
En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> que sea el botón Cancelar del control. Cada vez que el usuario presiona la tecla ESC, sin tener en cuenta que otro control en el formulario tiene el foco, se hace clic en un botón de cancelación. Habitualmente, este botón se programa para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-designate-the-cancel-button"></a>Para designar el botón Cancelar  
  
1.  Seleccione el formulario en el que reside el botón.  
  
2.  En el **propiedades** ventana, establezca el formato <xref:System.Windows.Forms.Form.CancelButton%2A> propiedad a la <xref:System.Windows.Forms.Button> nombre del control.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Responder a clics de botones en Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

---
title: "Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba7b6f8ff44763c19de1eac6d4be98bca75ff9f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador
En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> que sea el botón Aceptar, también conocido como el botón predeterminado del control. Cada vez que el usuario presiona la tecla ENTRAR, hacer clic en el botón predeterminado, sin tener en cuenta que otro control en el formulario tiene el foco. Las excepciones a esto son cuando el control tiene el foco es otro botón, en ese caso, se hace clic en el botón con el foco, o un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar  
  
1.  Seleccione el formulario en el que reside el botón.  
  
2.  En el **propiedades** ventana, establezca el formato <xref:System.Windows.Forms.Form.AcceptButton%2A> propiedad a la <xref:System.Windows.Forms.Button> nombre del control.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Responder a clics de botones en Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

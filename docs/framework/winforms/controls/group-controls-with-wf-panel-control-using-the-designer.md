---
title: "Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1d4a49f36ac294199871075a04b7e682bd5613b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador
Formularios Windows Forms <xref:System.Windows.Forms.Panel> controles se utilizan para agrupar otros controles. Hay tres razones para agrupar controles. Uno es visual de agrupación de elementos de formulario relacionados para una interfaz de usuario clara; otra razón es la programación de agrupación, de botones de radio, por ejemplo, el último es para mover los controles como una unidad en tiempo de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-group-of-controls"></a>Para crear un grupo de controles  
  
1.  Arrastre un <xref:System.Windows.Forms.Panel> controlar desde la **formularios Windows Forms** ficha del cuadro de herramientas hasta un formulario.  
  
2.  Agregar otros controles al panel, cada uno de ellos dentro del panel de dibujo.  
  
     Si dispone de los controles existentes que desee incluir en un panel, puede seleccionar todos los controles, como cortar a ellos en el Portapapeles, seleccione la <xref:System.Windows.Forms.Panel> de control y, a continuación, pegarlos en el panel. También puede arrastrar al panel.  
  
3.  (Opcional) Si desea agregar un borde a un panel, establezca su <xref:System.Windows.Forms.BorderStyle> propiedad. Hay tres opciones: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, y <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Vea también  
 [Panel (control)](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Establecer el fondo de un panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)

---
title: "C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para cancelar mediante el Dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "control de botón [Windows Forms], designar como botón para cancelar"
  - "botones, botones para cancelar"
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para cancelar mediante el Dise&#241;ador
En cualquier Windows Form, se puede designar un control <xref:System.Windows.Forms.Button> como el botón que se utiliza para cancelar.  Siempre que el usuario presione la tecla ESC hará clic en el botón para cancelar, independientemente del control del formulario que tenga el foco.  Habitualmente, este botón se programa para permitir que el usuario salga rápidamente de una operación sin confirmar ninguna acción.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para designar el botón para cancelar  
  
1.  Seleccione el formulario que contiene el botón.  
  
2.  En la ventana **Propiedades**, establezca en la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> del formulario en el nombre del control <xref:System.Windows.Forms.Button>.  
  
## Vea también  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
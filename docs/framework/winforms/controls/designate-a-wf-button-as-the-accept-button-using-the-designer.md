---
title: "C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para aceptar mediante el Dise&#241;ador | Microsoft Docs"
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
  - "Aceptar (botón de Windows Forms)"
  - "control de botón [Windows Forms], designar como predeterminado"
  - "botones, predeterminados en formularios Windows Forms"
  - "controles de Windows Forms, botón predeterminado en un formulario"
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Designar un bot&#243;n de formularios Windows Forms como bot&#243;n para aceptar mediante el Dise&#241;ador
En cualquier Windows Form, se puede designar un control <xref:System.Windows.Forms.Button> como el botón que se utiliza para aceptar, también conocido como botón predeterminado.  Siempre que el usuario presione la tecla ENTRAR hará clic en el botón predeterminado, independientemente del control del formulario que tenga el foco.  La excepción a esta regla se da cuando el control con el foco es otro botón \(en ese caso, se presionará el botón con el foco\) o un cuadro de texto de varias líneas o un control personalizado que acapare la tecla ENTRAR.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para designar el botón de aceptar  
  
1.  Seleccione el formulario que contiene el botón.  
  
2.  En la ventana **Propiedades**, establezca en la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario en el nombre del control <xref:System.Windows.Forms.Button>.  
  
## Vea también  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
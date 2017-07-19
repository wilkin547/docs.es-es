---
title: "Informaci&#243;n general sobre el control Label (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Label"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "imágenes [Windows Forms], mostrar en etiquetas"
  - "Label (control) [Windows Forms], acerca del control Label"
  - "etiquetas"
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el control Label (formularios Windows Forms)
Los controles <xref:System.Windows.Forms.Label> de formularios Windows Forms se utilizan para mostrar texto o imágenes que el usuario no puede editar.  Se utilizan para identificar objetos en un formulario; por ejemplo, para proporcionar una descripción de lo que hará cierto control si se hace clic en él o para mostrar información en respuesta a un evento o proceso en tiempo de ejecución de la aplicación.  Por ejemplo, puede utilizar etiquetas para agregar leyendas descriptivas a cuadros de texto, cuadros de lista, cuadros combinados, etc.  También puede escribir código que cambie el texto que muestra una etiqueta en respuesta a eventos en tiempo de ejecución.  Por ejemplo, si la aplicación tarda varios minutos en procesar un cambio, puede mostrar en una etiqueta un mensaje que notifique el estado de procesamiento del cambio.  
  
## Trabajar con el control de etiquetas  
 Dado que el control <xref:System.Windows.Forms.Label> no puede recibir el foco, puede utilizarse también para crear teclas de acceso para otros controles.  Una tecla de acceso permite al usuario seleccionar el otro control si presiona simultáneamente la tecla ALT y la tecla de acceso.  Para obtener más información, vea [Crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 La leyenda que se muestra en la etiqueta corresponde al valor de la propiedad <xref:System.Windows.Forms.Label.Text%2A>.  La propiedad <xref:System.Windows.Forms.Label.TextAlign%2A> permite establecer la alineación del texto dentro de la etiqueta.  Para obtener más información, vea [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.Label>   
 [Cómo: Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
---
title: "Mouse Capture in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "mouse, capture"
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Mouse Capture in Windows Forms
*Captura del mouse* hace referencia al momento en que un control dirige la entrada del mouse.  Cuando un control ha capturado el mouse, recibe la entrada del mouse de que el puntero se encuentre dentro de sus límites.  
  
## Establecer la captura del mouse  
 En Formularios Windows Forms el control captura el mouse si el usuario presiona un botón del mismo sobre un control, y lo libera si el usuario suelta el botón del mouse.  
  
 La propiedad <xref:System.Windows.Forms.Control.Capture%2A> de la clase <xref:System.Windows.Forms.Control> especifica si un control ha capturado el mouse.  Para determinar cuando un control pierde la captura del mouse, controle el evento <xref:System.Windows.Forms.Control.MouseCaptureChanged>.  
  
 Sólo la ventana de primer plano puede capturar el mouse.  Cuando la ventana de primer plano captura el mouse, la ventana recibe los mensajes sólo para los eventos del mouse que se producen cuando el puntero se encuentra dentro de la parte visible de la ventana.  Además, aunque la ventana de primer plano haya capturado el mouse, el usuario todavía puede hacer clic en otra ventana, colocándola en primer plano.  Cuando se captura el mouse, las teclas de método abreviado no funcionan.  
  
## Vea también  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
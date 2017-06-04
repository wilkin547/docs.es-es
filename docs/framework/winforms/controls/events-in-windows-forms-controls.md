---
title: "Eventos de los controles de formularios Windows Forms | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], información general sobre eventos (mediante código)"
  - "eventos [Windows Forms], controles personalizados (usando código)"
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Eventos de los controles de formularios Windows Forms
Los controles de formularios Windows Forms heredan más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Entre ésos se incluye el evento <xref:System.Windows.Forms.Control.Paint>, que produce que se dibuje un control, eventos relacionados con la presentación de una ventana, como los eventos <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout>, y eventos de teclado y de mouse de bajo nivel.  <xref:System.Windows.Forms.Control> sintetiza algunos eventos de bajo nivel en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>.  Para obtener información detallada sobre eventos heredados, vea <xref:System.Windows.Forms.Control>.  
  
 Si el control personalizado debe invalidar la funcionalidad de evento heredado, se debe invalidar el método `On`*nombreDeEvento* en lugar de asociar un delegado.  Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
## Vea también  
 [Reemplazar el método OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)   
 [Controlar la introducción de datos por el usuario](../../../../docs/framework/winforms/controls/handling-user-input.md)   
 [Definir un evento en los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [Eventos](../../../../docs/standard/events/index.md)
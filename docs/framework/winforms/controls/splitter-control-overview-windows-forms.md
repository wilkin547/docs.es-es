---
title: "Informaci&#243;n general sobre Splitter (Control, formularios Windows Forms) | Microsoft Docs"
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
  - "Splitter"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Splitter (control) [Windows Forms], acerca del control Splitter"
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre Splitter (Control, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque el control <xref:System.Windows.Forms.SplitContainer> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.Splitter> de las versiones anteriores, <xref:System.Windows.Forms.Splitter> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.  
  
 Los controles <xref:System.Windows.Forms.Splitter> de Windows Forms se utilizan para cambiar en tiempo de ejecución el tamaño de los controles acoplados.  El control <xref:System.Windows.Forms.Splitter> suele utilizarse en formularios con controles que contienen datos de longitud variable, como el Explorador de Windows, cuyos paneles de datos contienen información cuyo ancho cambia en función de las acciones del usuario.  
  
## Trabajar con el control divisor  
 Cuando el usuario sitúa el puntero del mouse sobre el borde desacoplado de un control cuyo tamaño puede cambiar por medio de un control divisor, el puntero cambia de apariencia para indicar que es posible cambiar el tamaño del control.  El control divisor permite al usuario cambiar el tamaño del control acoplado inmediatamente anterior.  Por lo tanto, para permitir al usuario cambiar el tamaño de un control acoplado en tiempo de ejecución, deberá acoplar al borde de un contenedor el control cuyo tamaño va a cambiar y, a continuación, acoplar un control Splitter al mismo lado del contenedor.  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [Cómo: Acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
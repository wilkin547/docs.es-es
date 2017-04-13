---
title: "Mouse Pointers in Windows Forms | Microsoft Docs"
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
  - "pointers, setting [Windows Forms]"
  - "mouse pointers"
  - "mouse cursors"
  - "mouse pointers, setting [Windows Forms]"
  - "cursors, setting [Windows Forms]"
  - "mouse, cursors"
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Mouse Pointers in Windows Forms
El *puntero* del mouse, al que a veces se denomina cursor, es un mapa de bits que especifica un punto de foco en la pantalla para la entrada de datos proporcionados por el usuario a través del mouse.  Este tema proporciona información general sobre el puntero del mouse en formularios Windows Forms y describe algunas formas de modificarlo y controlarlo.  
  
## Acceso al puntero del mouse  
 La clase <xref:System.Windows.Forms.Cursor> representa el puntero del mouse y cada <xref:System.Windows.Forms.Control> tiene una propiedad <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName> que especifica el puntero para ese control.  La clase <xref:System.Windows.Forms.Cursor> contiene las propiedades que describen el puntero, como <xref:System.Windows.Forms.Cursor.Position%2A> y <xref:System.Windows.Forms.Cursor.HotSpot%2A>, así como los métodos que pueden modificar la apariencia del puntero, como <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A> y <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## Controlar el puntero del mouse  
 Es posible que a veces desee limitar el área donde se puede utilizar el puntero del mouse o cambiar su posición.  Puede obtener o establecer la ubicación actual del mouse utilizando la propiedad <xref:System.Windows.Forms.Cursor.Position%2A> de <xref:System.Windows.Forms.Cursor>.  Además, puede limitar el área que puede utilizar el puntero del mouse estableciendo la propiedad <xref:System.Windows.Forms.Cursor.Clip%2A>.  El área de recorte, de manera predeterminada, es la pantalla completa.  
  
## Cambiar el puntero del mouse  
 Cambiar el puntero del mouse es una forma significativa de proporcionar información al usuario.  Por ejemplo, el puntero del mouse puede modificarse en los controladores de los eventos <xref:System.Windows.Forms.Control.MouseEnter> y <xref:System.Windows.Forms.Control.MouseLeave> para informar al usuario de los cálculos que se están realizando y para limitar la interacción del usuario en el control.  A veces, el puntero del mouse cambiará debido a eventos del sistema, por ejemplo cuando la aplicación realice operaciones de arrastrar y colocar.  
  
 La forma principal de cambiar el puntero del mouse es estableciendo <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName> o la propiedad <xref:System.Windows.Forms.Control.DefaultCursor%2A> de un control en un nuevo <xref:System.Windows.Forms.Cursor>.  Para obtener ejemplos para cambiar el puntero del mouse, vea el ejemplo de código en la clase <xref:System.Windows.Forms.Cursor>.  Además, la clase <xref:System.Windows.Forms.Cursors> expone un conjunto de objetos <xref:System.Windows.Forms.Cursor> para diferentes tipos de punteros, como el puntero que se muestra como una mano.  Para mostrar un puntero de espera, que se asemeja a un reloj de arena, siempre que el puntero del mouse esté sobre un control, utilice la propiedad <xref:System.Windows.Forms.Control.UseWaitCursor%2A> de la clase<xref:System.Windows.Forms.Control>.  
  
## Vea también  
 <xref:System.Windows.Forms.Cursor>   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Drag\-and\-Drop Functionality in Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
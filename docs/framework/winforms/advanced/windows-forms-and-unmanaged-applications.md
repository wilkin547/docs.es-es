---
title: "Windows Forms and Unmanaged Applications | Microsoft Docs"
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
  - "ActiveX controls [Windows Forms]"
  - "COM interop, Windows Forms"
  - "COM [Windows Forms]"
  - "Windows Forms, unmanaged"
  - "Windows Forms, interop"
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms and Unmanaged Applications
Los controles y aplicaciones de Windows Forms pueden interoperar con aplicaciones no administradas, con algunas advertencias.  Las secciones siguientes describen los escenarios y configuraciones que admiten y no admiten las aplicaciones y controles de Windows Forms.  
  
## En esta sección  
 [Información general sobre formularios Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Proporciona información general acerca de cómo utilizar e implementar controles de Windows Forms que funcionan con aplicaciones no administradas.  
  
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Proporciona un ejemplo de código que muestra cómo utilizar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> para ejecutar Windows Forms en una aplicación no administrada.  
  
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Proporciona un ejemplo de código que muestra cómo ejecutar Windows Forms en su propio subproceso.  
  
 Consulte también [Tutorial: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## Referencia  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>  
 Se utiliza para crear un subproceso independiente para Windows Forms.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>  
 Inicia un bucle de mensajes para un subproceso.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Calcula las referencias de llamadas desde una aplicación no administrada a un formulario.  
  
## Secciones relacionadas  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Proporciona información general acerca de cómo utilizar tipos de .NET Framework en aplicaciones no administradas.
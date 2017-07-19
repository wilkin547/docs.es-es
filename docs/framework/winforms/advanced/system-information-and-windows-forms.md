---
title: "System Information and Windows Forms | Microsoft Docs"
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
  - "domain names, retrieving"
  - "SystemInformation class [Windows Forms]"
  - "user names, retrieving"
  - "system information [Windows Forms]"
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# System Information and Windows Forms
A veces es necesario recopilar información acerca del equipo en el que se está ejecutando su aplicación para poder tomar decisiones en el código.  Por ejemplo, quizás tenga una función que sólo sea aplicable cuando se conecta a un dominio de red concreto; en este caso, necesitaría una manera de determinar el dominio y deshabilitar la función si el dominio no está presente.  
  
 Las aplicaciones de Windows Forms pueden utilizar la clase <xref:System.Windows.Forms.SystemInformation> para determinar varios aspectos sobre un equipo en tiempo de ejecución.  En el ejemplo siguiente se muestra cómo se utiliza la clase <xref:System.Windows.Forms.SystemInformation> para recuperar el nombre de usuario y su dominio mediante <xref:System.Windows.Forms.SystemInformation.UserName%2A> y <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 Todos los miembros de la clase <xref:System.Windows.Forms.SystemInformation> son de sólo lectura; no se puede modificar la configuración de un usuario.  Hay más de 100 miembros en esta clase que devuelven información muy variada, desde el número de monitores conectados al equipo \(<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>\) hasta el espaciado de los iconos en el Explorador de Windows \(<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> y <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>\).  
  
 Entre los miembros más útiles de la clase <xref:System.Windows.Forms.SystemInformation> se incluyen <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> y <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## Vea también  
 <xref:System.Windows.Forms.SystemInformation>   
 [Power Management in Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
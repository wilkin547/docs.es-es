---
title: Información del sistema y formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: 727bcc53750081ae2d957527332ed3199c7d8e8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="system-information-and-windows-forms"></a>Información del sistema y formularios Windows Forms
A veces es necesario recopilar información sobre el equipo que se ejecuta en la aplicación con el fin de tomar decisiones en el código. Por ejemplo, podría tener una función que solo es aplicable cuando se conecta a un dominio de red determinado; en este caso necesitaría una manera de determinar el dominio y deshabilitar la función si el dominio no está presente.  
  
 Las aplicaciones de formularios Windows Forms pueden utilizar la <xref:System.Windows.Forms.SystemInformation> clase para determinar un número de aspectos sobre un equipo en tiempo de ejecución. En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Forms.SystemInformation> clase para recuperar la <xref:System.Windows.Forms.SystemInformation.UserName%2A> y <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Todos los miembros de la <xref:System.Windows.Forms.SystemInformation> clase son de solo lectura; no se puede modificar la configuración de un usuario. Hay más de 100 miembros de la clase, devolver información en todo el contenido desde el número de monitores conectados al equipo (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) para el espaciado de los iconos en el Explorador de Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> y <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Algunos de los miembros más útiles de la <xref:System.Windows.Forms.SystemInformation> clase incluir <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, y <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SystemInformation>  
 [Administración de energía en Windows Forms](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)

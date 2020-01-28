---
title: Información de sistema
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
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732579"
---
# <a name="system-information-and-windows-forms"></a>Información del sistema y Windows Forms
A veces es necesario recopilar información sobre el equipo en el que se ejecuta la aplicación para tomar decisiones en el código. Por ejemplo, puede tener una función que solo es aplicable cuando se conecta a un dominio de red determinado. en este caso, necesitaría una manera de determinar el dominio y deshabilitar la función si el dominio no está presente.  
  
 Windows Forms aplicaciones pueden utilizar la clase <xref:System.Windows.Forms.SystemInformation> para determinar una serie de cosas sobre un equipo en tiempo de ejecución. En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Windows.Forms.SystemInformation> para recuperar los <xref:System.Windows.Forms.SystemInformation.UserName%2A> y <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 Todos los miembros de la clase <xref:System.Windows.Forms.SystemInformation> son de solo lectura; no se puede modificar la configuración de un usuario. Hay más de 100 miembros de la clase, que devuelven información sobre todo, desde el número de monitores conectados al equipo (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) hasta el espaciado de los iconos del explorador de Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> y <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Algunos de los miembros más útiles de la clase <xref:System.Windows.Forms.SystemInformation> incluyen <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>y <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SystemInformation>
- [Administración de energía en Windows Forms](power-management-in-windows-forms.md)

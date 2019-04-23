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
ms.openlocfilehash: eeb469dbf4553634aa50d0a9ea17e9b2464defb4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228905"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="7488b-102">Información del sistema y formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7488b-102">System Information and Windows Forms</span></span>
<span data-ttu-id="7488b-103">A veces es necesario recopilar información sobre el equipo que se está ejecutando en la aplicación con el fin de tomar decisiones en el código.</span><span class="sxs-lookup"><span data-stu-id="7488b-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="7488b-104">Por ejemplo, podría tener una función que solo es aplicable cuando se conecta a un dominio de red determinado; en este caso, necesitará una manera de determinar el dominio y deshabilitar la función de si el dominio no está presente.</span><span class="sxs-lookup"><span data-stu-id="7488b-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="7488b-105">Las aplicaciones de Windows Forms pueden usar el <xref:System.Windows.Forms.SystemInformation> clase para determinar un número de cosas acerca de un equipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7488b-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="7488b-106">El ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Forms.SystemInformation> clase para recuperar el <xref:System.Windows.Forms.SystemInformation.UserName%2A> y <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="7488b-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
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
  
 <span data-ttu-id="7488b-107">Todos los miembros de la <xref:System.Windows.Forms.SystemInformation> clase son de solo lectura; no se puede modificar la configuración de un usuario.</span><span class="sxs-lookup"><span data-stu-id="7488b-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="7488b-108">Hay más de 100 miembros de la clase, devolver información en todo el contenido desde el número de monitores conectados al equipo (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) para el espaciado de iconos en el Explorador de Windows (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> y <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="7488b-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="7488b-109">Algunos de los miembros más útiles de la <xref:System.Windows.Forms.SystemInformation> clase incluir <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, y <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="7488b-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7488b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7488b-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="7488b-111">Administración de energía en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7488b-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)

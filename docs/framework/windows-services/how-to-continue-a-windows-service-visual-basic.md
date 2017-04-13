---
title: "How to: Continue a Windows Service (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController.Continue"
helpviewer_keywords: 
  - "Windows Service applications, pausing"
  - "pausing Windows Service applications"
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 16
---
# How to: Continue a Windows Service (Visual Basic)
En este ejemplo se utiliza el componente <xref:System.ServiceProcess.ServiceController> para reanudar el servicio de administración de IIS en el equipo local.  
  
## Ejemplo  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows \> Servicios de Windows**.  Para obtener más información, vea [Fragmentos de código](../Topic/Code%20Snippets.md).  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencia de proyecto a System.serviceprocess.dll.  
  
-   Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>.  Agregar una instrucción `Imports` si no se incluyen nombres de miembro completos en el código.  Para obtener más información, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Programación eficaz  
 La propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> de la clase <xref:System.ServiceProcess.ServiceController> es el equipo local de forma predeterminada.  Para hacer referencia a los servicios de Windows de otro equipo, cambie la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> al nombre de ese equipo.  
  
 No se podrá llamar al método <xref:System.ServiceProcess.ServiceController.Continue%2A> en un servicio hasta que el estado del controlador de servicio sea <xref:System.ServiceProcess.ServiceControllerStatus>.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El servicio no se puede reanudar.  \(<xref:System.InvalidOperationException>\)  
  
-   Se ha producido un error en el acceso a una API del sistema.  \(<xref:System.ComponentModel.Win32Exception>\)  
  
## Seguridad de .NET Framework  
 El control de los servicios del equipo se puede restringir mediante el uso de la enumeración <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer los permisos de la clase <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 El acceso a la información del servicio se puede restringir mediante el uso de la enumeración <xref:System.Security.Permissions.PermissionState> para establecer los permisos de la clase <xref:System.Security.Permissions.SecurityPermission>.  
  
## Vea también  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 [How to: Pause a Windows Service \(Visual Basic\)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
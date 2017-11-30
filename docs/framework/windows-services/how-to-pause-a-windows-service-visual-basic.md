---
title: "Cómo: Pausar un servicio de Windows (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d44358d3f76f50a06ede5e7d720f4f48d80893de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Cómo: Pausar un servicio de Windows (Visual Basic)
Este ejemplo se utiliza la <xref:System.ServiceProcess.ServiceController> componente para pausar el servicio de administración de IIS en el equipo local.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **sistema operativo Windows > Servicios de Windows**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia de proyecto a System.serviceprocess.dll.  
  
-   Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad de la <xref:System.ServiceProcess.ServiceController> clase es el equipo local de forma predeterminada. Para hacer referencia a los servicios de Windows en otro equipo, cambie el <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad en el nombre de ese equipo.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede pausar el servicio. (<xref:System.InvalidOperationException>)  
  
-   Error de acceso a la API del sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Control de servicios en el equipo puede restringirse mediante el uso de la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer permisos en el <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 Acceso a la información del servicio puede restringirse mediante el uso de la <xref:System.Security.Permissions.PermissionState> para establecer permisos en el <xref:System.Security.Permissions.SecurityPermission>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [Cómo: continuar un servicio de Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)

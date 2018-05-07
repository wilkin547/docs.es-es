---
title: 'Cómo: Continuar un servicio de Windows (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
manager: douge
ms.openlocfilehash: 15ef15e0afe43d56db0972a686cd093e22c672dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Cómo: Continuar un servicio de Windows (Visual Basic)
Este ejemplo se utiliza la <xref:System.ServiceProcess.ServiceController> componente para reanudar el servicio de administración de IIS en el equipo local.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **sistema operativo Windows > Servicios de Windows**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia de proyecto a System.serviceprocess.dll.  
  
-   Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad de la <xref:System.ServiceProcess.ServiceController> clase es el equipo local de forma predeterminada. Para hacer referencia a los servicios de Windows en otro equipo, cambie el <xref:System.ServiceProcess.ServiceController.MachineName%2A> propiedad en el nombre de ese equipo.  
  
 No se puede llamar el <xref:System.ServiceProcess.ServiceController.Continue%2A> método en un servicio hasta que el estado del controlador de servicio es <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No se puede reanudar el servicio. (<xref:System.InvalidOperationException>)  
  
-   Error de acceso a la API del sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Control de servicios en el equipo puede restringirse mediante el uso de la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeración para establecer permisos en el <xref:System.ServiceProcess.ServiceControllerPermission> clase.  
  
 Acceso a la información del servicio puede restringirse mediante el uso de la <xref:System.Security.Permissions.PermissionState> enumeración para establecer permisos en el <xref:System.Security.Permissions.SecurityPermission> clase.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Pausa de un servicio de Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)

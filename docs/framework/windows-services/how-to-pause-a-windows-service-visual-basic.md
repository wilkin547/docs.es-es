---
title: Procedimiento para pausar un servicio de Windows (Visual Basic)
description: Lea cómo usar el componente ServiceController para pausar un servicio de Windows (como el Servicio de administración IIS) en un equipo local con Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
ms.openlocfilehash: 19919a8b0a289f0e88eb136d8c010a036e84cbec
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608509"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Procedimiento para pausar un servicio de Windows (Visual Basic)
En este ejemplo se utiliza el componente <xref:System.ServiceProcess.ServiceController> para pausar un servicio IIS Admin en el equipo local.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Servicios de Windows**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia de proyecto a System.serviceprocess.dll.  
  
- Acceso a los miembros del espacio de nombres <xref:System.ServiceProcess>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programación sólida  
 De manera predeterminada, la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> de la clase <xref:System.ServiceProcess.ServiceController> es el equipo local. Para hacer referencia a los servicios de Windows en otro equipo, cambie la propiedad <xref:System.ServiceProcess.ServiceController.MachineName%2A> al nombre de ese equipo.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
- No se puede pausar el servicio. (<xref:System.InvalidOperationException>)  
  
- Error de acceso a la API del sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 El control de servicios en el equipo puede restringirse con <xref:System.ServiceProcess.ServiceControllerPermissionAccess> para establecer los permisos en <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 El acceso a la información del servicio puede restringirse con <xref:System.Security.Permissions.PermissionState> para establecer los permisos en <xref:System.Security.Permissions.SecurityPermission>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [Cómo: Continuar un servicio de Windows (Visual Basic)](how-to-continue-a-windows-service-visual-basic.md)

---
title: Permisos peligrosos y administración de directivas
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b89792f9579da2d72c0a7f90a983308b172093fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390726"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Permisos peligrosos y administración de directivas
Varias de las operaciones protegidas para las que .NET Framework proporciona permisos pueden permitir potencialmente burlar el sistema de seguridad. Estos peligrosos permisos solo se deben conceder a código de confianza y únicamente cuando sea necesario. No suele haber ninguna defensa contra código malintencionado si se le conceden estos permisos.  
  
> [!NOTE]
>  En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]se introdujeron cambios importantes tanto en el modelo de seguridad de .NET Framework como en la terminología. Para obtener más información sobre estos cambios, consulte [cambios de seguridad](../../../docs/framework/security/security-changes.md).  
  
 Estos permisos peligrosos se explican en la tabla siguiente.  
  
|Permiso|Riesgo potencial|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Permite que el código administrado llame a código no administrado, lo que a menudo es peligroso.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Sin esta comprobación, el código puede hacer cualquier cosa.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|La evidencia no validada puede burlar la directiva de seguridad.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|La capacidad de modificar la directiva de seguridad puede deshabilitar la seguridad.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|El uso de serialización puede eludir los mecanismos de accesibilidad. Para obtener información más detallada, vea [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|La capacidad de establecer la entidad de seguridad actual puede engañar a la seguridad basada en roles.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|La manipulación de subprocesos es peligrosa debido al estado de seguridad asociado a ellos.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Puede utilizar miembros privados para anular los mecanismos de accesibilidad.|  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)

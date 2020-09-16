---
title: Permisos peligrosos y administración de directivas
description: Vea vínculos a los distintos permisos peligrosos en .NET. Estos permisos solo se deben proporcionar a código de confianza y solo cuando sea necesario.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: a2f4469590fea38924430b07eaf20d49f4dc46e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556946"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Permisos peligrosos y administración de directivas

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Varias de las operaciones protegidas para las que .NET Framework proporciona permisos pueden permitir potencialmente burlar el sistema de seguridad. Estos peligrosos permisos solo se deben conceder a código de confianza y únicamente cuando sea necesario. No suele haber ninguna defensa contra código malintencionado si se le conceden estos permisos.  
  
> [!NOTE]
> En el .NET Framework 4, ha habido cambios importantes en el modelo de seguridad .NET Framework y la terminología. Para obtener más información sobre estos cambios, consulte [cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes).  
  
 Estos permisos peligrosos se explican en la tabla siguiente.  
  
|Permiso|Riesgo potencial|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Permite que el código administrado llame a código no administrado, lo que a menudo es peligroso.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Sin esta comprobación, el código puede hacer cualquier cosa.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|La evidencia no validada puede burlar la directiva de seguridad.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|La capacidad de modificar la directiva de seguridad puede deshabilitar la seguridad.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|El uso de serialización puede eludir los mecanismos de accesibilidad. Para obtener información más detallada, vea [Seguridad y serialización](security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|La capacidad de establecer la entidad de seguridad actual puede engañar a la seguridad basada en roles.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|La manipulación de subprocesos es peligrosa debido al estado de seguridad asociado a ellos.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Puede utilizar miembros privados para anular los mecanismos de accesibilidad.|  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)

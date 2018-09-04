---
title: Seguridad en los formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 75016e9e04cf47782add18c87f7c677931743a4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556183"
---
# <a name="windows-forms-security"></a>Seguridad en los formularios Windows Forms
Windows Forms incluye un modelo de seguridad que está basado en código (niveles de seguridad se establecen para el código, independientemente del usuario que ejecuta el código). Esto es además de cualquier esquema de seguridad que pueda estar aplicada ya en el equipo. Estos pueden incluir en el explorador (por ejemplo, la seguridad basada en la zona de Internet Explorer) o el sistema operativo (por ejemplo, la seguridad basada en credenciales de Windows NT).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre la seguridad en Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 Explica brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para asegurarse de los formularios de Windows en la aplicación son seguros.  
  
 [Acceso más seguro a archivos y datos en Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 Describe cómo tener acceso a archivos y datos en un entorno de confianza parcial.  
  
 [Impresión más segura en Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 Describe cómo tener acceso a características de impresión en un entorno de confianza parcial.  
  
 [Consideraciones de seguridad adicionales en Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 Describe cómo manipular ventanas, usando el Portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [NIB: Directiva de seguridad predeterminada](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 Enumera los permisos concedidos en los conjuntos de permisos de plena confianza, Intranet Local e Internet.  
  
 [NIB: Administración de directiva de seguridad General](https://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 Proporciona información sobre la administración de la directiva de seguridad de .NET Framework y la concesión de permisos.  
  
 [Permisos peligrosos y administración de directivas](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 Se describen algunos de los permisos de.NET Framework que pueden permitir potencialmente burlar el sistema de seguridad.  
  
 [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)  
 Vínculos a temas que explican los procedimientos recomendados para escribir código seguro para .NET Framework.  
  
 [NIB: Solicitud de permisos](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 Describe el uso de atributos para que el tiempo de ejecución sepa qué permisos necesita ejecutar su código.  
  
 [Conceptos clave de seguridad](../../../docs/standard/security/key-security-concepts.md)  
 Vínculos a temas que tratan los aspectos básicos de seguridad del código.  
  
 [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)  
 Explica los fundamentos de trabajar con la directiva de seguridad de tiempo de ejecución de .NET Framework.  
  
 [NIB: Determinar cuándo se debe modificar la directiva de seguridad](https://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 Explica cómo determinar cuándo las aplicaciones necesitan desviarse de la directiva de seguridad predeterminada.  
  
 [NIB: Implementación de la directiva de seguridad](https://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 Describe la mejor manera de implementar cambios de directiva de seguridad.

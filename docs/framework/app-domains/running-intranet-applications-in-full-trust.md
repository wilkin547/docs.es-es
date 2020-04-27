---
title: Ejecutar aplicaciones de Intranet con plena confianza
ms.date: 03/30/2017
helpviewer_keywords:
- full trust, running intranet applications in
- intranet applications, running in full trust
- running intranet applications in full trust
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
ms.openlocfilehash: 33b025fa62343277fc96fc7771587e95f556e7a6
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645445"
---
# <a name="running-intranet-applications-in-full-trust"></a>Ejecutar aplicaciones de Intranet con plena confianza

A partir de .NET Framework versión 3.5 Service Pack 1 (SP1), las aplicaciones y sus ensamblados de biblioteca se pueden ejecutar como ensamblados de plena confianza desde un recurso compartido de red. Se agrega automáticamente la evidencia de zona <xref:System.Security.SecurityZone.MyComputer> a los ensamblados que se cargan desde un recurso compartido en la intranet. Esta evidencia proporciona a dichos ensamblados el mismo conjunto de permisos (generalmente, de plena confianza) que tienen los ensamblados que residen en el equipo. Esta funcionalidad no se aplica a las aplicaciones ClickOnce o a las aplicaciones que están diseñadas para ejecutarse en un host.  
  
## <a name="rules-for-library-assemblies"></a>Reglas de los ensamblados de biblioteca  

Las siguientes reglas se aplican a los ensamblados que se cargan mediante un ejecutable en un recurso compartido de red:  
  
- Los ensamblados de biblioteca deben residir en la misma carpeta que el ensamblado ejecutable. Los ensamblados que residen en una subcarpeta y los ensamblados a los que se hace referencia en una ruta de acceso diferente no reciben el conjunto de permisos de plena confianza.  
  
- Si el ejecutable retrasa la carga de un ensamblado, debe usar la misma ruta de acceso que se ha usado para iniciar el ejecutable. Por ejemplo, si el recurso compartido \\\\*network-computer*\\*share* se asigna a una letra de unidad y el ejecutable se ejecuta desde esa ruta de acceso, no se concederá plena confianza a los ensamblados cargados por el ejecutable mediante la ruta de red. Para retrasar la carga de un ensamblado en la zona <xref:System.Security.SecurityZone.MyComputer>, el ejecutable debe usar la ruta de acceso de letra de unidad.  
  
## <a name="restoring-the-former-intranet-policy"></a>Restaurar la directiva de intranet anterior  

En versiones anteriores de .NET Framework, se concedía evidencia de zona <xref:System.Security.SecurityZone.Intranet> a los ensamblados compartidos. Había que especificar la directiva de seguridad de acceso del código para conceder plena confianza a un ensamblado en un recurso compartido.  
  
Este nuevo comportamiento es el predeterminado para los ensamblados de la intranet. Puede volver al comportamiento anterior de proporcionar evidencia <xref:System.Security.SecurityZone.Intranet>. Para ello, establezca una clave del Registro que se aplique a todas las aplicaciones del equipo. Este proceso es diferente para equipos de 32 bits y de 64 bits:  
  
- En equipos de 32 bits, cree una subclave en la clave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework en el Registro del sistema. Use el nombre de clave LegacyMyComputerZone con un valor DWORD de 1.  
  
- En equipos de 64 bits, cree una subclave en la clave HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework en el Registro del sistema. Use el nombre de clave LegacyMyComputerZone con un valor DWORD de 1. Cree la misma subclave en la clave HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework.  
  
## <a name="see-also"></a>Vea también

- [Programar con ensamblados](../../standard/assembly/index.md)

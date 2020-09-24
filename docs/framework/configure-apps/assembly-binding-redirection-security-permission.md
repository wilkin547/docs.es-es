---
title: Permiso de seguridad para la redirección de enlaces de ensamblados
description: Obtenga información sobre el permiso de seguridad requerido para la redirección de enlace de ensamblados explícita en un archivo de configuración de la aplicación en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: 2de2c50f5adb9e9fa36ea015ef498e9953c83005
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165226"
---
# <a name="assembly-binding-redirection-security-permission"></a>Permiso de seguridad para la redirección de enlaces de ensamblados

Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad. Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores. El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> . De forma predeterminada, los ensamblados administrados no tienen permisos.  
  
 El permiso de seguridad se concede a las aplicaciones que se ejecutan en la zona de confianza (equipo local) y en la zona de intranet. Las aplicaciones que se ejecutan en la zona de Internet están estrictamente prohibidas para realizar la redirección de enlace de ensamblados.  
  
 El permiso no es necesario si la redirección de ensamblados se realiza en un archivo de directiva de edición que está controlado por el publicador de componentes o en el archivo de configuración del equipo controlado por el administrador. Sin embargo, el permiso es necesario para que una aplicación ignore explícitamente la Directiva de editor mediante el [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) elemento del archivo de configuración de la aplicación.  
  
 En la tabla siguiente se muestra la configuración de seguridad predeterminada para la marca **BindingRedirects** .  
  
|Zona|Valor de la marca BindingRedirects|  
|----------|-----------------------------------|  
|Zona de confianza (equipo local)|**ON**|  
|Zona Intranet|**ON**|  
|Zona de Internet|**OFF**|  
|Zonas que no son de confianza|**OFF**|  
  
 Un administrador puede cambiar esta configuración de seguridad para admitir o restringir escenarios específicos en un equipo determinado. No hay ninguna herramienta para cambiar la configuración de la marca **BindingRedirects** del valor predeterminado; un administrador debe editar manualmente el archivo de Security.config en el equipo de un usuario.  
  
## <a name="see-also"></a>Consulte también

- [Archivos de directivas de edición y ejecución en paralelo](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](how-to-enable-and-disable-automatic-binding-redirection.md)
- [Ejecución en paralelo](../deployment/side-by-side-execution.md)

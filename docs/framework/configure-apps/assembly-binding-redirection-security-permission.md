---
title: Permiso de seguridad para la redirección de enlaces de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: 25b74de66fbf053b4d9129ab6ca0bef1530bf228
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083761"
---
# <a name="assembly-binding-redirection-security-permission"></a>Permiso de seguridad para la redirección de enlaces de ensamblados
Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad. Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores. El permiso se otorga estableciendo el <xref:System.Security.Permissions.SecurityPermissionFlag> marca en el <xref:System.Security.Permissions.SecurityPermission>. Los ensamblados administrados no tienen permisos de forma predeterminada.  
  
 Se concede el permiso de seguridad para aplicaciones que se ejecutan en la zona de confianza (equipo local) y la zona de Intranet. Aplicaciones que se ejecutan en la zona de Internet se prohíbe estrictamente realiza la redirección de enlace de ensamblado.  
  
 El permiso no es necesario si se realiza la redirección de ensamblado en un archivo de directiva de edición que se controla mediante el Editor de componentes, o en el archivo de configuración de máquina que esté controlado por el administrador. Sin embargo, el permiso es necesario para una aplicación omitir explícitamente la directiva de publicador con el [ \<publisherPolicy aplicar = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación.  
  
 En la tabla siguiente se muestra el valor predeterminado de configuración de seguridad para el **BindingRedirects** marca.  
  
|Zona|Indicador BindingRedirects|  
|----------|-----------------------------------|  
|Zona de confianza (equipo local)|**ON**|  
|Zona de intranet|**ON**|  
|Zona de Internet|**OFF**|  
|Zonas de confianza|**OFF**|  
  
 Un administrador puede cambiar esta configuración de seguridad para admitir o rechazar escenarios específicos en un equipo determinado. No hay ninguna herramienta para cambiar la **BindingRedirects** marca predeterminado; un administrador debe editar manualmente el archivo Security.config en el equipo del usuario.  
  
## <a name="see-also"></a>Vea también
- [Archivos de directivas de publicador y ejecución en paralelo](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)
- [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
- [Ejecución en paralelo](../../../docs/framework/deployment/side-by-side-execution.md)

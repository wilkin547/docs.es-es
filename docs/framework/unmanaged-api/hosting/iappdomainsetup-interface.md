---
title: IAppDomainSetup (Interfaz)
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbde873481aea9de94862117a99079301965f33c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220076"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup (Interfaz)
Proporciona propiedades que permiten al host configurar un <xref:System.AppDomain?displayProperty=nameWithType> tipo antes de llamar a la [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) método para crearlo.  
  
## <a name="properties"></a>Propiedades  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Obtiene o establece el nombre del directorio que contiene la aplicación.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Obtiene o establece el nombre de la aplicación.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Obtiene o establece el nombre de un área específica de la aplicación donde los archivos se copia sombra.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Obtiene o establece el nombre del archivo de configuración para una aplicación.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Obtiene o establece el nombre del directorio donde se almacenan y se tiene acceso a los archivos generados dinámicamente.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Obtiene o establece la ruta de acceso al archivo de licencia que está asociado a este dominio.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Obtiene o establece la lista de directorios que se combina con la <xref:System.AppDomainSetup.ApplicationBase%2A> directorio para buscar ensamblados privados.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Obtiene o establece un valor de cadena que incluye o excluye <xref:System.AppDomainSetup.ApplicationBase%2A> desde la ruta de acceso de búsqueda para la aplicación.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Obtiene o establece los nombres de los directorios que contienen los ensamblados para que sea una copia sombra.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Obtiene o establece una cadena que indica si copia sombra está activada o desactivada. Los valores válidos son "true" o "false".|  
  
## <a name="remarks"></a>Comentarios  
 El `IAppDomainSetup` interfaz corresponde a los recursos administrados <xref:System.IAppDomainSetup> interfaz, es posible que el <xref:System.AppDomainSetup> escriba implementa. Consulte <xref:System.IAppDomainSetup?displayProperty=nameWithType> para obtener descripciones detalladas de sus propiedades.  
  
 `IAppDomainSetup` representa la información de enlace de ensamblado que se puede agregar a un <xref:System.AppDomain> instancia antes de su creación. Por ejemplo, un host puede establecer el <xref:System.AppDomainSetup.ApplicationBase%2A> ensamblados administrados de propiedad para establecer un directorio raíz, que busca common language runtime (CLR).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

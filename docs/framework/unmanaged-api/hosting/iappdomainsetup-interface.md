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
ms.openlocfilehash: 1726f8929404e0dde979972d7830a6951dd71891
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617066"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup (Interfaz)
Proporciona propiedades que permiten al host configurar un <xref:System.AppDomain?displayProperty=nameWithType> tipo antes de llamar al método [ICorRuntimeHost:: createdomainex (](icorruntimehost-createdomainex-method.md) para crearlo.  
  
## <a name="properties"></a>Propiedades  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Obtiene o establece el nombre del directorio que contiene la aplicación.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Obtiene o establece el nombre de la aplicación.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Obtiene o establece el nombre de un área específica de la aplicación donde se realiza la copia sombra de los archivos.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Obtiene o establece el nombre del archivo de configuración de una aplicación.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Obtiene o establece el nombre del directorio donde se almacenan los archivos generados dinámicamente y se obtiene acceso a ellos.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Obtiene o establece la ruta de acceso al archivo de licencia asociado a este dominio.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Obtiene o establece la lista de directorios combinados con el <xref:System.AppDomainSetup.ApplicationBase%2A> directorio en el que se buscarán los ensamblados privados.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Obtiene o establece un valor de cadena que incluye o excluye <xref:System.AppDomainSetup.ApplicationBase%2A> de la ruta de acceso de búsqueda para la aplicación.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Obtiene o establece los nombres de los directorios que contienen los ensamblados de los que se va a realizar la instantánea.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Obtiene o establece una cadena que indica si la copia sombra está activada o desactivada. Los valores válidos son "true" o "false".|  
  
## <a name="remarks"></a>Observaciones  
 La `IAppDomainSetup` interfaz corresponde a la interfaz administrada <xref:System.IAppDomainSetup> , que <xref:System.AppDomainSetup> implementa el tipo. Vea <xref:System.IAppDomainSetup?displayProperty=nameWithType> para obtener descripciones detalladas de sus propiedades.  
  
 `IAppDomainSetup`representa la información de enlace del ensamblado que se puede Agregar a una <xref:System.AppDomain> instancia antes de su creación. Por ejemplo, un host puede establecer la <xref:System.AppDomainSetup.ApplicationBase%2A> propiedad para establecer un directorio raíz, en el que el Common Language Runtime (CLR) sondea para los ensamblados administrados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Interfaces de hospedaje](hosting-interfaces.md)

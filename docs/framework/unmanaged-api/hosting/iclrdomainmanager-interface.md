---
title: ICLRDomainManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 797b6031449672e8b610b2a53e77497e5835ea6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657433"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager (Interfaz)
Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[SetAppDomainManagerType (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> (clase), del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.|  
|[SetPropertiesForDefaultAppDomain (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Establece las propiedades que se utilizará para inicializar el dominio de aplicación predeterminado.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener una instancia de esta interfaz, llame a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método con el tipo de administrador IID `IID_ICLRDomainManager`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)

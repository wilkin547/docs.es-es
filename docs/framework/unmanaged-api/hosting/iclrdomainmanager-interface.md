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
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681176"
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager (Interfaz)

Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[SetAppDomainManagerType (Método)](iclrdomainmanager-setappdomainmanagertype-method.md)|Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.|  
|[Método SetPropertiesForDefaultAppDomain](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.|  
  
## <a name="remarks"></a>Comentarios  

 Para obtener una instancia de esta interfaz, llame al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) con el IID de tipo de administrador `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)

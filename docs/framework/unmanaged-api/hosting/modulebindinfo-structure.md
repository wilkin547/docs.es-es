---
title: ModuleBindInfo (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 399ba2471b4dc7c5e372a56a9dcab8117068a693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo (Estructura)
Proporciona información detallada sobre el módulo que se hace referencia y el ensamblado que lo contiene.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para la `IStream` devuelto por una llamada a la [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) método desde el que se puede cargar el módulo que se hace referencia.|  
|`lpAssemblyIdentity`|Un identificador único para el ensamblado que contiene el módulo que se hace referencia.|  
|`lpModuleName`|El nombre del módulo que se hace referencia.|  
  
## <a name="remarks"></a>Comentarios  
 `ModuleBindInfo`se pasa como un parámetro para `IHostAssemblyStore::ProvideModule`. El host proporciona el identificador único `dwAppDomainId` a common language runtime (CLR). Después de llamar a la [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) método vuelve, el tiempo de ejecución utiliza el identificador para determinar si el contenido de la `IStream` se han asignado. Si es así, el tiempo de ejecución carga la copia existente en lugar de volver a asignar la secuencia. El tiempo de ejecución también utiliza este identificador como una clave de búsqueda para las secuencias que se devuelven de las llamadas a la `IHostAssemblyStore::ProvideAssembly` método. Por lo tanto, el identificador debe ser único para las solicitudes de módulo, así como para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.idl  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [AssemblyBindInfo (estructura)](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)

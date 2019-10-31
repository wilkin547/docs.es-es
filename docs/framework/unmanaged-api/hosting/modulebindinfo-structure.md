---
title: ModuleBindInfo (Estructura)
ms.date: 03/30/2017
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
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133746"
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo (Estructura)
Proporciona información detallada sobre el módulo al que se hace referencia y el ensamblado que lo contiene.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para el `IStream` devuelto por una llamada al método [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) desde el que se va a cargar el módulo al que se hace referencia.|  
|`lpAssemblyIdentity`|Un identificador único para el ensamblado que contiene el módulo al que se hace referencia.|  
|`lpModuleName`|Nombre del módulo al que se hace referencia.|  
  
## <a name="remarks"></a>Comentarios  
 `ModuleBindInfo` se pasa como parámetro a `IHostAssemblyStore::ProvideModule`. El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR). Después de que se devuelva una llamada al método [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) , el motor en tiempo de ejecución utiliza el identificador para determinar si se ha asignado el contenido de la `IStream`. En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia. El motor en tiempo de ejecución también utiliza este identificador como clave de búsqueda para las secuencias devueltas por las llamadas al método `IHostAssemblyStore::ProvideAssembly`. Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [AssemblyBindInfo (estructura)](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)

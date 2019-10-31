---
title: AssemblyBindInfo (Estructura)
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192113"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo (Estructura)
Proporciona información detallada acerca del ensamblado al que se hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para el `IStream` devuelto por una llamada a [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), desde el que se va a cargar el ensamblado al que se hace referencia.|  
|`lpReferencedIdentity`|Identificador único para el ensamblado al que se hace referencia.|  
|`lpPostPolicyIdentity`|Identificador del ensamblado al que se hace referencia después de la aplicación de los valores de directiva de enlace.|  
|`ePolicyLevel`|Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) que indican qué directivas de control de versiones, si las hay, deben aplicarse al ensamblado al que se hace referencia.|  
  
## <a name="remarks"></a>Comentarios  
 El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR). Después de que una llamada a `IHostAssemblyStore::ProvideAssembly` devuelve, el motor en tiempo de ejecución utiliza el identificador para determinar si se ha asignado el contenido de la `IStream`. En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia. El Runtime también utiliza este identificador como clave de búsqueda para las secuencias devueltas por las llamadas a [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo (estructura)](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)

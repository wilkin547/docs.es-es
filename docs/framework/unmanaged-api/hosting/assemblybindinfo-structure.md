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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f4cb71e5ac0afe19e865ffca6fe578ad08f3162
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773870"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo (Estructura)
Proporciona información detallada sobre el ensamblado que se hace referencia.  
  
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para el `IStream` devuelto por una llamada a [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), desde la que tiene que se puede cargar el ensamblado que se hace referencia.|  
|`lpReferencedIdentity`|Un identificador único para el ensamblado que se hace referencia.|  
|`lpPostPolicyIdentity`|El identificador para el ensamblado que se hace referencia después de la aplicación de los valores de directiva de enlace.|  
|`ePolicyLevel`|Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores que indican qué directivas de control de versiones, si los hay, deben aplicarse al ensamblado que se hace referencia.|  
  
## <a name="remarks"></a>Comentarios  
 El host proporciona el identificador único `dwAppDomainId` a common language runtime (CLR). Después de llamar a `IHostAssemblyStore::ProvideAssembly` devuelve, el tiempo de ejecución utiliza el identificador para determinar si el contenido de la `IStream` se han asignado. Si es así, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia. El tiempo de ejecución también utiliza este identificador como una clave de búsqueda para las secuencias devuelven por las llamadas a [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.idl  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo (estructura)](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)

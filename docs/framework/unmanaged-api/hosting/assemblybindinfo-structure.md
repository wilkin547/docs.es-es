---
description: 'Más información acerca de: estructura Assemblybindinfo ('
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
ms.openlocfilehash: 3e11e05924ee6818737f84d9ca92394ee5313292
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799985"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para el `IStream` devuelto por una llamada a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md), desde el que se va a cargar el ensamblado al que se hace referencia.|  
|`lpReferencedIdentity`|Identificador único para el ensamblado al que se hace referencia.|  
|`lpPostPolicyIdentity`|Identificador del ensamblado al que se hace referencia después de la aplicación de los valores de directiva de enlace.|  
|`ePolicyLevel`|Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) que indican qué directivas de control de versiones, si las hay, deben aplicarse al ensamblado al que se hace referencia.|  
  
## <a name="remarks"></a>Observaciones  

 El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR). Después de una llamada a `IHostAssemblyStore::ProvideAssembly` , el tiempo de ejecución utiliza el identificador para determinar si `IStream` se ha asignado el contenido de. En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia. El Runtime también utiliza este identificador como clave de búsqueda para las secuencias devueltas por las llamadas a [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md). Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](hosting-structures.md)
- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](ihostassemblymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
- [ModuleBindInfo (Estructura)](modulebindinfo-structure.md)

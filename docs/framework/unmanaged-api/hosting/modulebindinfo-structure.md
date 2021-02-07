---
description: 'Más información acerca de: estructura Modulebindinfo ('
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
ms.openlocfilehash: 0969c0ecc459414336800e8e7da5817ac0c1a8ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679633"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwAppDomainId`|Un identificador único para el `IStream` devuelto por una llamada al método [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) desde el que se va a cargar el módulo al que se hace referencia.|  
|`lpAssemblyIdentity`|Un identificador único para el ensamblado que contiene el módulo al que se hace referencia.|  
|`lpModuleName`|Nombre del módulo al que se hace referencia.|  
  
## <a name="remarks"></a>Observaciones  

 `ModuleBindInfo` se pasa como un parámetro a `IHostAssemblyStore::ProvideModule` . El host proporciona el identificador único `dwAppDomainId` al Common Language Runtime (CLR). Después de que se devuelva una llamada al método [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) , el motor en tiempo de ejecución utiliza el identificador para determinar si `IStream` se ha asignado el contenido de. En ese caso, el tiempo de ejecución carga la copia existente en lugar de reasignar la secuencia. El Runtime también utiliza este identificador como clave de búsqueda para las secuencias que se devuelven desde las llamadas al `IHostAssemblyStore::ProvideAssembly` método. Por lo tanto, el identificador debe ser único para las solicitudes de módulo y para las solicitudes de ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](hosting-structures.md)
- [AssemblyBindInfo (Estructura)](assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](ihostassemblymanager-interface.md)

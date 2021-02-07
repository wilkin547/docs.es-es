---
description: 'Más información acerca de: IHostMemoryManager:: CreateMAlloc ((método)'
title: IHostMemoryManager::CreateMAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: de73490a5c8b4e1672beb4750bcc617c2371f07b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707895"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a>IHostMemoryManager::CreateMAlloc (Método)

Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) que se utiliza para hacer solicitudes de asignación de un montón creado por el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwMallocType`  
 de Combinación de marcas de [MALLOC_TYPE](malloc-type-enumeration.md) que especifica las características de la memoria que se va a asignar.  
  
 `ppMAlloc`  
 enuncia Puntero a la dirección de una `IHostMAlloc` instancia de proporcionada por el host.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateMAlloc` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria física disponible para completar la solicitud de asignación.|  
  
## <a name="remarks"></a>Observaciones  

 `CreateMAlloc` Devuelve un objeto que permite que CLR realice solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMalloc (Interfaz)](ihostmalloc-interface.md)
- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)

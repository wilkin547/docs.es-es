---
title: IHostMemoryManager::VirtualFree (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: be006afaf5966aa4e6d11c73b92004d676c97c7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731272"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree (Método)

Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualFree` libera, anula la confirmación o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `lpAddress`  
 de Puntero a la dirección base de las páginas de memoria virtual que se van a liberar.  
  
 `dwSize`  
 de Tamaño, en bytes, de la región que se va a liberar.  
  
 `dwFreeType`  
 de Tipo de operación de liberación.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`VirtualFree` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|Se intentó liberar memoria que no se asignó a través del host.|  
  
## <a name="remarks"></a>Comentarios  

 `VirtualFree` libera las páginas de memoria virtual asociadas al `lpAddress` parámetro a través de una llamada anterior a la función [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) . Los intentos de liberar memoria que no se asignaron a través del host deben devolver HOST_E_INVALIDOPERATION.  
  
 La semántica es idéntica a la de la implementación de Win32 de `VirtualFree` . Para obtener más información, vea la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [IHostMalloc (Interfaz)](ihostmalloc-interface.md)

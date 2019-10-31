---
title: IHostMemoryManager::VirtualAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
ms.openlocfilehash: dd588fa85ff8aaa396a8d0e52a738ada46c2a9b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128608"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc (Método)
Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAddress`  
 de Puntero a la dirección inicial de la región que se va a asignar.  
  
 `dwSize`  
 de Tamaño, en bytes, de la región.  
  
 `flAllocationType`  
 de Tipo de asignación de memoria.  
  
 `flProtect`  
 de Protección de memoria para la región de páginas que se va a asignar.  
  
 `dwCriticalLevel`  
 de Un valor [ememorycriticallevel (](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) que indica el impacto de un error de asignación.  
  
 `ppMem`  
 enuncia Puntero a la dirección inicial de la memoria asignada, o null si no se puede satisfacer la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para completar la solicitud de asignación|  
  
## <a name="remarks"></a>Comentarios  
 Para reservar una región en el espacio de direcciones del proceso, llame a `VirtualAlloc`. El parámetro `pAddress` contiene la dirección inicial del bloque de memoria que desee. Normalmente, este parámetro se establece en NULL. El sistema operativo mantiene un registro de los intervalos de direcciones libres disponibles para el proceso. Un valor de `pAddress` null indica al sistema que Reserve la región donde sea adecuado. Como alternativa, puede proporcionar una dirección de inicio específica para el bloque de memoria. En ambos casos, se devuelve el parámetro de salida `ppMem` como un puntero a la memoria asignada. La propia función devuelve un valor HRESULT.  
  
 La función `VirtualAlloc` de Win32 no tiene un parámetro `ppMem` y devuelve el puntero a la memoria asignada en su lugar. Para obtener más información, vea la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

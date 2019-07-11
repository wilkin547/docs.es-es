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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a0764cb212a95412a4dcf9455b7648ee863951e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767665"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc (Método)
Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.  
  
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
 [in] Un puntero a la dirección inicial de la región para asignar.  
  
 `dwSize`  
 [in] El tamaño, en bytes, de la región.  
  
 `flAllocationType`  
 [in] El tipo de asignación de memoria.  
  
 `flProtect`  
 [in] Protección de memoria para la región de páginas asignadas.  
  
 `dwCriticalLevel`  
 [in] Un [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valor que indica el impacto de un error de asignación.  
  
 `ppMem`  
 [out] Puntero a la dirección inicial de la memoria asignada, o null si no se pudo satisfacer la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para completar la solicitud de asignación|  
  
## <a name="remarks"></a>Comentarios  
 Reservar una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc`. El `pAddress` parámetro contiene la dirección del principio del bloque de memoria que desee. Este parámetro normalmente se establece en null. El sistema operativo mantiene un registro de los intervalos de direcciones libres disponibles para su proceso. Un `pAddress` valor null indica al sistema que reserve la región dondequiera que considere adecuada. Como alternativa, puede proporcionar una dirección de inicio específica para el bloque de memoria. En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada. La propia función devuelve un valor HRESULT.  
  
 Win32 `VirtualAlloc` función no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar. Para obtener más información, consulte la documentación de la plataforma de Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

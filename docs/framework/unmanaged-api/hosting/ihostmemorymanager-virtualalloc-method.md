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
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440319"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc (Método)
Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAddress`  
 [in] Un puntero a la dirección inicial de la región para asignar.  
  
 `dwSize`  
 [in] El tamaño, en bytes, de la región.  
  
 `flAllocationType`  
 [in] El tipo de asignación de memoria.  
  
 `flProtect`  
 [in] Protección de la memoria para la región de páginas que se va a asignar.  
  
 `dwCriticalLevel`  
 [in] Un [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valor que indica el impacto de un error de asignación.  
  
 `ppMem`  
 [out] Puntero a la dirección inicial de la memoria asignada, o null si no se pudo satisfacer la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para completar la solicitud de asignación|  
  
## <a name="remarks"></a>Comentarios  
 Para reservar una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc`. El `pAddress` parámetro contiene la dirección del principio del bloque de memoria que desee. Este parámetro se establece normalmente en null. El sistema operativo mantiene un registro de intervalos de direcciones libres disponibles para el proceso. Un `pAddress` valor null indica al sistema que reserve la región dondequiera que considere apropiada. Como alternativa, puede proporcionar una dirección inicial concreta para el bloque de memoria. En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada. La propia función devuelve un valor HRESULT.  
  
 Win32 `VirtualAlloc` la función no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar. Para obtener más información, consulte la documentación de la plataforma de Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

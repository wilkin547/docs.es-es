---
title: IHostMAlloc::DebugAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178037"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc (Método)
Solicita que el host asigne la cantidad especificada de memoria del montón y, además, realice un seguimiento de dónde se asignó la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbSize`  
 [en] El tamaño, en bytes, de la solicitud de asignación de memoria actual.  
  
 `dwCriticalLevel`  
 [en] Uno de los [eMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indica el impacto de un error de asignación.  
  
 `pszFileName`  
 [en] El archivo de código del ejecutable que se está depurando.  
  
 `iLineNo`  
 [en] El número `pszFileName` de línea en el que se solicitó la asignación.  
  
 `ppMem`  
 [fuera] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`regresó con éxito.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para completar la solicitud de asignación.|  
  
## <a name="remarks"></a>Observaciones  
 El CLR obtiene un puntero de interfaz a un [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia mediante una llamada a la [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método. `DebugAlloc`permite que el tiempo de ejecución obtenga información de archivo de código para su uso durante la depuración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)

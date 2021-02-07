---
description: 'Más información acerca de: IHostMAlloc::D método ebugAlloc'
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
ms.openlocfilehash: f94ff0d6cc1e25daee12c67c38167f7f14829510
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708221"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc (Método)

Solicita que el host asigne la cantidad de memoria especificada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.  
  
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
 de Tamaño, en bytes, de la solicitud de asignación de memoria actual.  
  
 `dwCriticalLevel`  
 de Uno de los valores de [ememorycriticallevel (](ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.  
  
 `pszFileName`  
 de El archivo de código del ejecutable que se está depurando.  
  
 `iLineNo`  
 de El número de línea en el `pszFileName` que se solicitó la asignación.  
  
 `ppMem`  
 enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`DebugAlloc` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para completar la solicitud de asignación.|  
  
## <a name="remarks"></a>Observaciones  

 CLR obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) . `DebugAlloc` permite al motor en tiempo de ejecución obtener información del archivo de código para su uso durante la depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [IHostMalloc (Interfaz)](ihostmalloc-interface.md)

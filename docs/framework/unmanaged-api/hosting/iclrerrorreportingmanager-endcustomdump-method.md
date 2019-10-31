---
title: ICLRErrorReportingManager::EndCustomDump (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
ms.openlocfilehash: 2acbe72377e4c5b291ab062fcb5faa6503bd7937
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129294"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a>ICLRErrorReportingManager::EndCustomDump (Método)
Quita la configuración de volcado de la pila personalizada que se especificó en una llamada anterior al método [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`EndCustomDump` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El método `EndCustomDump` borra la configuración de volcado de pila personalizada establecida por una llamada anterior al método `BeginCustomDump` y libera cualquier estado asociado. Se debe llamar después de completar el volcado de la pila personalizado.  
  
> [!IMPORTANT]
> Si no se llama a `EndCustomDump`, se produce una pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CustomDumpItem (estructura)](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [ECustomDumpFlavor (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)

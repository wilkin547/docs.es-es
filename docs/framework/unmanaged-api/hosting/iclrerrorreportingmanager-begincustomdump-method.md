---
description: 'Más información acerca de: ICLRErrorReportingManager:: BeginCustomDump (método)'
title: ICLRErrorReportingManager::BeginCustomDump (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 3f8498068d50ffc6ea00cf4f08f969c92f010d6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689487"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump (Método)

Especifica la configuración de volcados de montón personalizados para el informe de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwFlavor`  
 de Un valor [ecustomdumpflavor (](ecustomdumpflavor-enumeration.md) que indica el tipo de volcado del montón en el que se va a generar el volcado del montón personalizado.  
  
 `dwNumItems`  
 de Longitud de la `items` matriz. Si `dwFlavor` no es DUMP_FLAVOR_Mini, `dwNumItems` debe ser cero.  
  
 `items`  
 de Una matriz de instancias de [customdumpitem (](customdumpitem-structure.md) , que especifica los elementos que se van a agregar al minivolcado. Si `dwFlavor` no es DUMP_FLAVOR_Mini, `items` debe ser null.  
  
 `dwReserved`  
 [in] Reservado para uso futuro.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 El `BeginCustomDump` método establece la configuración personalizada del volcado del montón. El método [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) borra la configuración de volcado del montón personalizado y libera cualquier estado asociado. Se debe llamar después de que se complete el volcado del montón personalizado.  
  
> [!IMPORTANT]
> Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CustomDumpItem (Estructura)](customdumpitem-structure.md)
- [ECustomDumpFlavor (Enumeración)](ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager (Interfaz)](iclrerrorreportingmanager-interface.md)

---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5c03b7010418f75aff984102d7fa4fb089c4d59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738823"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)
Lo llama [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para notificar al depurador el resultado de un intento de enumerar un área especificada de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [in] La dirección inicial de la región de memoria que se van a enumerar.  
  
 `size`  
 [in] El tamaño, en bytes, de la región de memoria.  
  
## <a name="remarks"></a>Comentarios  
 El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar un área de memoria. La enumeración continuará incluso si este método devuelve un HRESULT que indica un error.  
  
 Las áreas notificadas por esta devolución de llamada pueden ser duplicados o superpuestas regiones.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataEnumMemoryRegionsCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)

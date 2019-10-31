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
ms.openlocfilehash: 2ebe7ef37fb072e3688cc4dcfa5ed89832e886e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122934"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)
Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 de Dirección inicial de la región de memoria que se va a enumerar.  
  
 `size`  
 de Tamaño, en bytes, de la región de memoria.  
  
## <a name="remarks"></a>Comentarios  
 El método `ICLRDataEnumMemoryRegions::EnumMemoryRegions` llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria. La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.  
  
 Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataEnumMemoryRegionsCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)

---
description: 'Más información sobre: ICLRDataEnumMemoryRegionsCallback (:: Enummemoryregion ((método)'
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
ms.openlocfilehash: 733911f71898ea7019a0b8d854fb1c1bf61a2474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801402"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion (Método)

Llamado por [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) para informar al depurador del resultado de un intento de enumerar un área de memoria especificada.  
  
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
  
## <a name="remarks"></a>Observaciones  

 El `ICLRDataEnumMemoryRegions::EnumMemoryRegions` método llamará a este método de devolución de llamada después de cada intento de enumerar una región de memoria. La enumeración continuará incluso si este método devuelve un valor HRESULT que indica un error.  
  
 Las regiones que se declaran mediante esta devolución de llamada pueden ser duplicados o regiones superpuestas.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataEnumMemoryRegionsCallback (Interfaz)](iclrdataenummemoryregionscallback-interface.md)

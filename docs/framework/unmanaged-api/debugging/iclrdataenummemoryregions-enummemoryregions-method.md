---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 693ec07176f80711709cd9b85c6886bea8be74b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122965"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)
Enumera las áreas de memoria especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `callback`  
 de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.  
  
 La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.  
  
 `miniDumpFlags`  
 de No se usa.  
  
 `clrFlags`  
 de Un valor de la enumeración [clrdataenummemoryflags (](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.  
  
## <a name="remarks"></a>Comentarios  
 Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataEnumMemoryRegions (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)

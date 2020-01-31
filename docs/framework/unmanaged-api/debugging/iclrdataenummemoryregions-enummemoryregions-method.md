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
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785638"
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
  
## <a name="parameters"></a>Parameters  
 `callback`  
 de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.  
  
 La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.  
  
 `miniDumpFlags`  
 de No se usa.  
  
 `clrFlags`  
 de Un valor de la enumeración [clrdataenummemoryflags (](clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.  
  
## <a name="remarks"></a>Notas  
 Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataEnumMemoryRegions (interfaz)](iclrdataenummemoryregions-interface.md)

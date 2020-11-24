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
ms.openlocfilehash: 386f975ab0bbbe804fda2bd7567acf24f69e77fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676080"
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
 de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.  
  
 La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.  
  
 `miniDumpFlags`  
 [in] No se utiliza.  
  
 `clrFlags`  
 de Un valor de la enumeración [clrdataenummemoryflags (](clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.  
  
## <a name="remarks"></a>Comentarios  

 Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRDataEnumMemoryRegions (Interfaz)](iclrdataenummemoryregions-interface.md)

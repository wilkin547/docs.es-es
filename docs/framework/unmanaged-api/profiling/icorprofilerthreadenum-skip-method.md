---
title: ICorProfilerThreadEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: 4218faf1c324175424ab20305224f7f2fa51bb7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494220"
---
# <a name="icorprofilerthreadenumskip-method"></a>ICorProfilerThreadEnum::Skip (Método)
Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de Número de elementos que se van a omitir.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`celt`se omitieron los elementos.|  
|S_FALSE|`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.|  
  
## <a name="remarks"></a>Comentarios  
 La nueva posición del cursor de este enumerador es (posición actual) + `celt` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerThreadEnum (Interfaz)](icorprofilerthreadenum-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)

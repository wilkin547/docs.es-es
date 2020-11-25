---
title: ICorProfilerInfo3::GetStringLayout2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: dc4df7e7cb93f137013d0a0e4d805c7563d4fe1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697901"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a>ICorProfilerInfo3::GetStringLayout2 (Método)

Obtiene información sobre la distribución de un objeto de cadena. Este método reemplaza al método [ICorProfilerInfo2:: GetStringLayout (](icorprofilerinfo2-getstringlayout-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pStringLengthOffset`  
 enuncia Puntero al desplazamiento de la ubicación, en relación con el `ObjectID` puntero, que almacena la longitud de la propia cadena. La longitud se almacena como un `DWORD` .  
  
 `pBufferOffset`  
 enuncia Puntero al desplazamiento del búfer, en relación con el `ObjectID` puntero, que almacena la cadena de caracteres anchos.  
  
## <a name="remarks"></a>Comentarios  

 Las cadenas pueden o no terminar en NULL.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)

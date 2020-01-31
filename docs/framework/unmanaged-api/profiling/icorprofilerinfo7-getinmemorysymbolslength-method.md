---
title: 'ICorProfilerInfo7:: GetInMemorySymbolsLength (método)'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868361"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7:: GetInMemorySymbolsLength (método)
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Devuelve la longitud de una secuencia de símbolos en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleId`  
 de Identificador del módulo que contiene la secuencia en memoria.  
  
 pCountSymbolBytes  
 enuncia Un puntero a un valor de `DWORD` que, cuando el método vuelve, contiene la longitud de la secuencia en bytes.  
  
## <a name="return-value"></a>Valor devuelto  
 El método devuelve `S_OK` si se puede determinar la longitud de la secuencia de memoria, incluso si es cero (0).  
  
 El método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` si el método se creó utilizando <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Notas  
 Si el módulo tiene símbolos en memoria, la longitud de la secuencia se coloca en `pCountSymbolBytes`. Si el módulo no tiene símbolos en memoria, `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
> La implementación actual no admite Reflection. Emit. Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo7 (interfaz)](icorprofilerinfo7-interface.md)

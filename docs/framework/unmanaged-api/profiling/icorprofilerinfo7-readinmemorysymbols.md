---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955372"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Lee bytes de una secuencia de símbolos en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de Identificador del módulo que contiene la secuencia en memoria.  
  
 `symbolsReadOffset`  
 de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.  
  
 `pSymbolBytes`  
 enuncia Puntero al búfer en el que se copiarán los datos. El búfer debe tener `countSymbolBytes` espacio disponible.  
  
 `countSymbolBytes`  
 de Número de bytes que se van a copiar.  
  
 `pCountSymbolBytesRead`  
 enuncia Cuando el método vuelve, contiene el número real de bytes leídos.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`es si se leyó un número distinto de cero de bytes.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se ha creado <xref:System.Reflection.Emit>con.  
  
## <a name="remarks"></a>Comentarios  
 El `ReadInMemorySymbols` método intenta leer `countSymbolBytes` los datos a partir del desplazamiento `symbolsReadOffset` en la secuencia en memoria. Los datos se copian `pSymbolBytes`en, lo que se espera `countSymbolBytes` que tenga espacio disponible.     `pCountSymbolsBytesRead`contiene el número real de bytes leídos, que puede ser menor `countSymbolBytes` que si se alcanza el final de la secuencia.  
  
> [!NOTE]
> La implementación actual no admite Reflection. Emit. Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

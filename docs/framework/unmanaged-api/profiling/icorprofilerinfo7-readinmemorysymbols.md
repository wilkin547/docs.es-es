---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ada9f629c3a3c3d8b7c32ebc180c4788b6f6d3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[compatible con la versión [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] y posteriores]  
  
 Lee los bytes de una secuencia de símbolos en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo que contiene la secuencia en memoria.  
  
 `symbolsReadOffset`  
 [in] El desplazamiento dentro de la secuencia en memoria en el que se va a comenzar la lectura de bytes.  
  
 `pSymbolBytes`  
 [out] Un puntero al búfer al que se copiarán los datos. Debe tener el búfer `countSymbolBytes` de espacio disponible.  
  
 `countSymbolBytes`  
 [in] El número de bytes que se va a copiar.  
  
 `pCountSymbolBytesRead`  
 [out] Cuando el método vuelve, contiene el número real de bytes leídos.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`, si un número distinto de cero de bytes leído.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, si se creó el módulo mediante <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Comentarios  
 El `ReadInMemorySymbols` método intenta leer `countSymbolBytes` de datos a partir del desplazamiento `symbolsReadOffset` dentro de la secuencia en memoria. Los datos se copian en `pSymbolBytes`, lo que se esperaba que `countSymbolBytes` de espacio disponible.     `pCountSymbolsBytesRead`contiene el número real de bytes leídos, lo que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.  
  
> [!NOTE]
>  La implementación actual no admite Reflection.Emit. Si se creó el módulo mediante Reflection.Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaz ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

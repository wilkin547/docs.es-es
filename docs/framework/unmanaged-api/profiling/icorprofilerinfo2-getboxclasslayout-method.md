---
title: ICorProfilerInfo2::GetBoxClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: ff39a688132112e88438bc192d7c1ab61f169400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727164"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>ICorProfilerInfo2::GetBoxClassLayout (Método)

Obtiene información sobre dónde se encuentra el tipo de valor especificado cuando se le aplica la conversión boxing.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parámetros  

 `classId`  
 de IDENTIFICADOR de la clase que describe el tipo de valor al que se aplica la conversión boxing.  
  
 `pBufferOffset`  
 enuncia Entero que es el desplazamiento con respecto al puntero de identificador de objeto con conversión boxing del tipo de valor.  
  
## <a name="remarks"></a>Comentarios  

 El `pBufferOffset` valor es la ubicación del tipo de valor dentro de un cuadro. Una vez `pBufferOffset` que se aplica a un objeto con conversión boxing, el diseño de clase del tipo de valor se puede utilizar para interpretar el valor del objeto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)

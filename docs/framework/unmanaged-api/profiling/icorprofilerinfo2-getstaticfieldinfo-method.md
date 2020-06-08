---
title: ICorProfilerInfo2::GetStaticFieldInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: e1dd6addd9053ffb6cf2ce23408673d8fca17cb5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496846"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo (Método)
Obtiene un valor que indica el tipo de estático que se aplica al campo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 de IDENTIFICADOR de la clase en la que se define el campo estático.  
  
 `fieldToken`  
 de El símbolo (token) de metadatos para el campo estático.  
  
 `pFieldInfo`  
 enuncia Un puntero a un valor de la enumeración [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) que indica si el campo especificado es estático y, en ese caso, el tipo de estático que se aplica al campo.  
  
## <a name="remarks"></a>Comentarios  
 Esta información se puede usar para determinar la función a la que se va a llamar para obtener la dirección del campo estático.  
  
 El código del generador de perfiles debe seguir comprobando los metadatos de un campo estático para asegurarse de que realmente tiene una dirección. Los literales estáticos (es decir, las constantes) solo existen en los metadatos y no tienen una dirección.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)

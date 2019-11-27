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
ms.openlocfilehash: e74bab058adda759db1fb549022608eedfef5d80
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432973"
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
 enuncia Un puntero a un valor de la enumeración [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) que indica si el campo especificado es estático y, en ese caso, el tipo de estático que se aplica al campo.  
  
## <a name="remarks"></a>Comentarios  
 Esta información se puede usar para determinar la función a la que se va a llamar para obtener la dirección del campo estático.  
  
 El código del generador de perfiles debe seguir comprobando los metadatos de un campo estático para asegurarse de que realmente tiene una dirección. Los literales estáticos (es decir, las constantes) solo existen en los metadatos y no tienen una dirección.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

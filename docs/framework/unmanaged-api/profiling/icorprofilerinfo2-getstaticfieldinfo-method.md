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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2ab0d482366b037f92a55f00dd33df8a312e84b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo (Método)
Obtiene un valor que indica el tipo de estática que se aplica al campo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de la clase en la que se define el campo estático.  
  
 `fieldToken`  
 [in] El token de metadatos para el campo estático.  
  
 `pFieldInfo`  
 [out] Un puntero a un valor de la [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeración que indica si el campo especificado es estático y, si es así, el tipo de estática que se aplica al campo.  
  
## <a name="remarks"></a>Comentarios  
 Esta información puede utilizarse para determinar a qué función llamar para obtener la dirección del campo estático.  
  
 El código del generador de perfiles debería comprobar los metadatos de un campo estático para asegurarse de que realmente tiene una dirección. Los literales estáticos (es decir, constantes) sólo existen en los metadatos y no tiene una dirección.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

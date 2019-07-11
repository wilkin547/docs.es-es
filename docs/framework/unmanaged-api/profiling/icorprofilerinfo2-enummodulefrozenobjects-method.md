---
title: ICorProfilerInfo2::EnumModuleFrozenObjects (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e044a9dedf96025981c1a77471c6abedfc26420
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762375"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>ICorProfilerInfo2::EnumModuleFrozenObjects (Método)
Obtiene un enumerador que permite la iteración a través de los objetos inmovilizados en el módulo especificado. Este método está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El identificador del módulo que contiene los objetos inmovilizados que hay que enumerar.  
  
 `ppEnum`  
 [out] Un puntero a la dirección de un [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaz, que enumera los objetos inmovilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

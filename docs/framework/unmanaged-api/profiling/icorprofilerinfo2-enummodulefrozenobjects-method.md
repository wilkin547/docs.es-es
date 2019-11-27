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
ms.openlocfilehash: 51e0c5b08b8a2ac3b8eaf38cdabd682078ba70c8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436051"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>ICorProfilerInfo2::EnumModuleFrozenObjects (Método)
Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado. Este método está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleID`  
 de IDENTIFICADOR del módulo que contiene los objetos inmovilizados que se van a enumerar.  
  
 `ppEnum`  
 enuncia Puntero a la dirección de una interfaz [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) , que enumera los objetos inmovilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 3,5, 3,0 sp1, 3,0, 2,0 sp1, 2,0  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

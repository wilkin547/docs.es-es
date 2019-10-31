---
title: 'ICorProfilerInfo7:: ApplyMetaData (método)'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130350"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: ApplyMetaData (método)
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Aplica los metadatos recién definidos por los métodos `IMetadataEmit::Define*` a un módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleID`  
 de Identificador del módulo cuyos metadatos se cambiaron.  
  
## <a name="remarks"></a>Comentarios  
 Si se realizan cambios en los metadatos después de la devolución de llamada [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) , debe llamar a este método antes de usar los nuevos metadatos.  
  
 `ApplyMetaData` solo admite agregar los siguientes tipos de metadatos:  
  
- `AssemblyRef` registros, que se crean mediante una llamada a [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). .  
  
- `TypeRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit:: GetTokenFromTypeSpec (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .  

A partir de .NET Core 3,0, `ApplyMetaData` también admite los siguientes tipos:

- `TypeDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) . Sin embargo, no se admite la adición de métodos virtuales a un tipo existente. Los métodos virtuales deben agregarse antes de la devolución de llamada [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

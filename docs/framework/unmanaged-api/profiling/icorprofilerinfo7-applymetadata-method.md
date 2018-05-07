---
title: 'Icorprofilerinfo7:: Applymetadata (método)'
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b8b6ba429a45c92dc6b6b5dcaa7c8a35b47385f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Icorprofilerinfo7:: Applymetadata (método)
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Se aplica a los metadatos recién definidos por el `IMetadataEmit::Define*` métodos a un módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El identificador del módulo cuyos metadatos se cambió.  
  
## <a name="remarks"></a>Comentarios  
 Si se realizan cambios en los metadatos después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada, debe llamar a este método antes de usar los nuevos metadatos.  
  
 `ApplyMetaData` solo admite la adición de los siguientes tipos de metadatos:  
  
-   `AssemblyRef` registros, lo que se crean mediante una llamada a la [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). .  
  
-   `TypeRef` registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) método.  
  
-   `TypeSpec` registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.  
  
-   `MemberRef` registros, lo que se crean mediante una llamada a la [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método.  
  
-   `MemberSpec` registros, lo que se crean mediante una llamada a la [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) método.  
  
-   `UserString` registros, lo que se crean mediante una llamada a la [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)

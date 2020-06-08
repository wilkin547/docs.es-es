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
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495514"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: ApplyMetaData (método)
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.  
  
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
 Si se realizan cambios en los metadatos después de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , debe llamar a este método antes de usar los nuevos metadatos.  
  
 `ApplyMetaData`solo admite la adición de los siguientes tipos de metadatos:  
  
- `AssemblyRef`registros, que se crean mediante una llamada a [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md). .  
  
- `TypeRef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec`registros, que se crean mediante una llamada al método [IMetaDataEmit:: GetTokenFromTypeSpec (](../metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec`registros, que se crean mediante una llamada al método [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .  

A partir de .NET Core 3,0, `ApplyMetaData` también admite los siguientes tipos:

- `TypeDef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) . Sin embargo, no se admite la adición de métodos virtuales a un tipo existente. Los métodos virtuales deben agregarse antes de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaz ICorProfilerInfo7](icorprofilerinfo7-interface.md)

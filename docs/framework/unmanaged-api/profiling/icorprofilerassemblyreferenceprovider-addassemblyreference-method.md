---
description: 'Más información sobre: ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference (método)'
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: e73a6d59b76744dcf9f4991be2589220669e154d
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760749"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Informa al Common Language Runtime (CLR) de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a>Parámetros

`pAssemblyRefInfo` Puntero a una estructura de [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) que proporciona a CLR información sobre una referencia de ensamblado que debe tener en cuenta al realizar un recorrido de cierre de referencia de ensamblado.
  
## <a name="remarks"></a>Observaciones  

 El generador de perfiles llama a este método para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en el `wszAssemblyPath` argumento de la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) . El objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) se pasa a la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) del generador de perfiles, junto con la ruta de acceso y el nombre del ensamblado en el `wszAssemblyPath` argumento.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerAssemblyReferenceProvider (Interfaz)](icorprofilerassemblyreferenceprovider-interface.md)
- [GetAssemblyReferences (método)](icorprofilercallback6-getassemblyreferences-method.md)
- [Método ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)

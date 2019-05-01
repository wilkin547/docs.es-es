---
title: ICorProfilerCallback6::GetAssemblyReferences (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5296fbab71c67572718a58fedb9f89b064f816
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041501"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>ICorProfilerCallback6::GetAssemblyReferences (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszAssemblyPath`  
 [in] Ruta de acceso y nombre del ensamblado cuyos metadatos se modificarán.  
  
 `pAsmRefProvider`  
 [in] Un puntero a la dirección de un [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interfaz que especifica el ensamblado hace referencia a agregar.  
  
## <a name="return-value"></a>Valor devuelto  
 Los valores devueltos de esta devolución de llamada se pasan por alto.  
  
## <a name="remarks"></a>Comentarios  
 Esta devolución de llamada se controla estableciendo la [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) marca de máscara de eventos cuando se llama a la [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método. Si se registra el generador de perfiles para el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) el método de devolución de llamada, el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto de interfaz a ese método. El generador de perfiles, a continuación, puede llamar a la [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) método con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino tiene previsto hacer referencia desde el ensamblado especificado en el `GetAssemblyReferences` devolución de llamada.  
  
 Use la devolución de llamada `GetAssemblyReferences` solo si el generador de perfiles tiene que modificar los metadatos de un ensamblado para agregar referencias de ensamblado. (Pero tenga en cuenta que la modificación real de los metadatos de un ensamblado se realiza en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)método de devolución de llamada.) El generador de perfiles deben implementar el método de devolución de llamada `GetAssemblyReferences` para informar a Common Language Runtime (CLR) que se agregarán referencias de ensamblado cuando el módulo se haya cargado.  Esto garantiza que las decisiones que tome CLR acerca del uso compartido de ensamblados en esta fase temprana seguirán siendo válidas aunque el generador de perfiles tenga planeado modificar las referencias de ensamblado de metadatos más adelante.  De esta manera se pueden evitar algunas instancias en las que las modificaciones de los metadatos del generador de perfiles provocan un error `SECURITY_E_INCOMPATIBLE_SHARE`.  
  
 El generador de perfiles usa el [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto proporcionado por este método para agregar referencias de ensamblado para el Rastreador de cierres de referencia de ensamblado CLR.  El [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto debe usarse únicamente desde dentro de esta devolución de llamada. Las llamadas a la [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) método desde esta devolución de llamada no tienen como resultado los metadatos modificados, pero sólo en un rastreo de cierre de referencias de ensamblado modificado. El generador de perfiles aún tendrá que usar un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) objeto va a agregar explícitamente las referencias de ensamblado desde el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada para hacer referencia ensamblado, incluso si implementa el `GetAssemblyReferences` devolución de llamada.  
  
 El generador de perfiles debe estar preparado para recibir llamadas duplicadas a esta devolución de llamada para el mismo ensamblado y debe responder de forma idéntica para cada de estas llamadas duplicadas (realizando el mismo conjunto de [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) llamadas).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback6 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)
- [ModuleLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
- [ICorProfilerAssemblyReferenceProvider (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)

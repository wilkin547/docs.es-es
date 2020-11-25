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
ms.openlocfilehash: c9e973009f46ef7e554ee2df63493464f4956342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725487"
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
 de Puntero a la dirección de una interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) que especifica las referencias de ensamblado que se van a agregar.  
  
## <a name="return-value"></a>Valor devuelto  

 Los valores devueltos de esta devolución de llamada se pasan por alto.  
  
## <a name="remarks"></a>Comentarios  

 Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) . Si el generador de perfiles se registra para el método de devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a ese método. Después, el generador de perfiles puede llamar al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en la `GetAssemblyReferences` devolución de llamada.  
  
 Use la devolución de llamada `GetAssemblyReferences` solo si el generador de perfiles tiene que modificar los metadatos de un ensamblado para agregar referencias de ensamblado. (Pero tenga en cuenta que la modificación real de los metadatos de un ensamblado se realiza en el método de devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)). El generador de perfiles debe implementar el `GetAssemblyReferences` método de devolución de llamada para informar al Common Language Runtime (CLR) que se agregarán referencias de ensamblado cuando se haya cargado el módulo.  Esto garantiza que las decisiones que tome CLR acerca del uso compartido de ensamblados en esta fase temprana seguirán siendo válidas aunque el generador de perfiles tenga planeado modificar las referencias de ensamblado de metadatos más adelante.  De esta manera se pueden evitar algunas instancias en las que las modificaciones de los metadatos del generador de perfiles provocan un error `SECURITY_E_INCOMPATIBLE_SHARE`.  
  
 El generador de perfiles usa el objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) proporcionado por este método para agregar referencias de ensamblado al rastreador de cierre de referencia de ensamblado de CLR.  El objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) solo debe usarse desde esta devolución de llamada. Las llamadas al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) desde esta devolución de llamada no dan como resultado metadatos modificados, sino solo en un recorrido de cierre de referencia de ensamblado modificado. El generador de perfiles todavía tendrá que usar un objeto [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) para agregar explícitamente las referencias de ensamblado desde dentro de la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) para el ensamblado de referencia, aunque implemente la `GetAssemblyReferences` devolución de llamada.  
  
 El generador de perfiles debe estar preparado para recibir llamadas duplicadas a esta devolución de llamada para el mismo ensamblado y debe responder de forma idéntica para cada una de estas llamadas duplicadas (realizando el mismo conjunto de llamadas a [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback6 (Interfaz)](icorprofilercallback6-interface.md)
- [Método ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)](cor-prf-assembly-reference-info-structure.md)
- [ICorProfilerAssemblyReferenceProvider (Interfaz)](icorprofilerassemblyreferenceprovider-interface.md)

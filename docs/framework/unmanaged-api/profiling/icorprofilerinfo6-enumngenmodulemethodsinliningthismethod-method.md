---
title: "ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cf0bccebbfe5620ef329cc8c6f72582a7afe85a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)
[Compatible con .NET Framework 4.6 y versiones posteriores]  
  
 Devuelve un enumerador para todos los métodos que se definen en un determinado módulo de NGen y en línea un método determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `inlinersModuleId`  
 [in] El identificador de un módulo NGen.  
  
 `inlineeModuleId`  
 [in] El identificador de un módulo que define `inlineeMethodId`. Vea la sección Comentarios para obtener más información.  
  
 `inlineeMethodId`  
 [in] El identificador de un método entre línea. Vea la sección Comentarios para obtener más información.  
  
 `incompleteData`  
 [out] Una marca que indica si `ppEnum` contiene todos los métodos de inserción de un método determinado.  Vea la sección Comentarios para obtener más información.  
  
 `ppEnum`  
 [out] Un puntero a la dirección de un enumerador  
  
## <a name="remarks"></a>Comentarios  
 `inlineeModuleId`y `inlineeMethodId` juntos forman el identificador completo para el método que podría estar entre línea. Por ejemplo, suponga módulo `A` define un método `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 módulo Bdefines y `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Supongamos también que `Fancy.AddTwice` elementos incorporados en la llamada a `SimpleAdd`. Un generador de perfiles podría utilizar este enumerador para buscar todos los métodos definen en el módulo B qué alineado `Simple.Add`, y el resultado podría enumerar `AddTwice`.  `inlineeModuleId`es el identificador del módulo `A`, y `inlineeeMethodId` es el identificador de `Simple.Add(int a, int b)`.  
  
 Si `incompleteData` es true después de la función devuelve el enumerador no contiene todos los métodos de inserción un método determinado. Esto puede suceder cuando uno o más dependencias directas o indirectas del módulo inliners aún no se han cargado todavía. Si un generador de perfiles necesita datos precisos, debe reintentar más tarde cuando se cargan varios módulos, preferiblemente en cada carga de módulo.  
  
 El `EnumNgenModuleMethodsInliningThisMethod` método se puede utilizar para evitar limitaciones en la inclusión de ReJIT. ReJIT permite un generador de perfiles cambie la implementación de un método y, a continuación, crear código nuevo para el mismo sobre la marcha. Por ejemplo, podríamos cambiar `Simple.Add` como se indica a continuación:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Sin embargo porque `Fancy.AddTwice` tiene ya insertadas `Simple.Add`, sigue teniendo el mismo comportamiento que antes. Para evitar esa limitación, el llamador tiene que buscar todos los métodos en todos los módulos que en línea `Simple.Add` y usar `ICorProfilerInfo5::RequestRejit` en cada uno de estos métodos. Cuando los métodos se volverán a compilar, tendrán el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaz ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)

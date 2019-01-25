---
title: Icorprofilerinfo6 (método)
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568158"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Icorprofilerinfo6 (método)
[Compatible con .NET Framework 4.6 y versiones posteriores]  
  
 Devuelve un enumerador para todos los métodos que se definen en un determinado módulo NGen y en línea un método determinado.  
  
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
 [in] El identificador de un método entre líneas. Vea la sección Comentarios para obtener más información.  
  
 `incompleteData`  
 [out] Una marca que indica si `ppEnum` contiene todos los métodos de inserción de un método determinado.  Vea la sección Comentarios para obtener más información.  
  
 `ppEnum`  
 [out] Un puntero a la dirección de un enumerador  
  
## <a name="remarks"></a>Comentarios  
 `inlineeModuleId` y `inlineeMethodId` juntos forman el identificador completo para el método que podría insertarse. Por ejemplo, suponga módulo `A` define un método `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 módulo Bdefines y `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Supongamos también que `Fancy.AddTwice` elementos incorporados en la llamada a `SimpleAdd`. Un generador de perfiles podría utilizar este enumerador para buscar todos los métodos definen en el módulo B en qué línea `Simple.Add`, y el resultado podría enumerar `AddTwice`.  `inlineeModuleId` es el identificador del módulo `A`, y `inlineeeMethodId` es el identificador de `Simple.Add(int a, int b)`.  
  
 Si `incompleteData` es true después de la función que devuelve el enumerador no contiene todos los métodos de inserción un método determinado. Esto puede suceder cuando uno o más dependencias directas o indirectas de módulo inliners aún no se ha cargado aún. Si un generador de perfiles necesita datos precisos, debe a intentarlo más tarde cuando se cargan más módulos, preferiblemente en cada carga de módulo.  
  
 El `EnumNgenModuleMethodsInliningThisMethod` método puede utilizarse para solucionar las limitaciones de inclusión entre líneas para ReJIT. ReJIT permite a un generador de perfiles cambie la implementación de un método y, a continuación, crear código nuevo para ella sobre la marcha. Por ejemplo, podríamos cambiar `Simple.Add` como sigue:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Sin embargo porque `Fancy.AddTwice` tiene ya insertadas `Simple.Add`, sigue teniendo el mismo comportamiento como antes. Para solucionar esta limitación, el llamador tiene que buscar todos los métodos en todos los módulos directamente `Simple.Add` y usar `ICorProfilerInfo5::RequestRejit` en cada uno de esos métodos. Cuando los métodos se volverán a compilar, tendrá el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo6 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)

---
description: 'Más información sobre: ICorProfilerInfo6:: EnumNgenModuleMethodsInliningThisMethod (método)'
title: Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: bd43dcecabe9a75f7ce3a94996727b192574e321
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737173"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod

Devuelve un enumerador a todos los métodos que se definen en un módulo NGen determinado e inserta un método determinado.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>Parámetros

`inlinersModuleId`\
de Identificador de un módulo NGen.

`inlineeModuleId`\
de Identificador de un módulo que define `inlineeMethodId` . Vea la sección Comentarios para obtener más información.

`inlineeMethodId`\
de Identificador de un método insertado. Vea la sección Comentarios para obtener más información.

`incompleteData`\
enuncia Marca que indica si `ppEnum` contiene todos los métodos que inlinean un método determinado.  Vea la sección Comentarios para obtener más información.

`ppEnum`\
enuncia Puntero a la dirección de un enumerador.

## <a name="remarks"></a>Observaciones

`inlineeModuleId` y `inlineeMethodId` forman conjuntamente el identificador completo para el método que podría estar insertado. Por ejemplo, Imagine que `A` el módulo define un método `Simple.Add` :

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

y el módulo B define `Fancy.AddTwice` :

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

También se supone que `Fancy.AddTwice` inserta la llamada a `SimpleAdd` . Un generador de perfiles podría usar este enumerador para buscar todos los métodos definidos en el módulo B que están alineados `Simple.Add` y el resultado Enumeraría `AddTwice` .  `inlineeModuleId` es el identificador del módulo `A` y `inlineeMethodId` es el identificador de `Simple.Add(int a, int b)` .

Si `incompleteData` es true después de que la función devuelva un valor, el enumerador no contiene todos los métodos que inlinean un método determinado. Esto puede ocurrir cuando todavía no se han cargado una o más dependencias directas o indirectas del módulo inlineers. Si un generador de perfiles necesita datos precisos, debe volver a intentarlo más tarde cuando se carguen más módulos, preferiblemente en cada carga de módulo.

El `EnumNgenModuleMethodsInliningThisMethod` método se puede usar para solucionar las limitaciones de la inserción de ReJIT. ReJIT permite que un generador de perfiles cambie la implementación de un método y, a continuación, cree código nuevo sobre la marcha. Por ejemplo, podríamos cambiar de la `Simple.Add` siguiente manera:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Sin embargo `Fancy.AddTwice` , dado que ya se ha insertado `Simple.Add` , sigue teniendo el mismo comportamiento que antes. Para solucionar esta limitación, el llamador tiene que buscar todos los métodos en todos los módulos que se alinean `Simple.Add` y usan `ICorProfilerInfo5::RequestRejit` en cada uno de esos métodos. Cuando se vuelven a compilar los métodos, tendrán el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo6](icorprofilerinfo6-interface.md)

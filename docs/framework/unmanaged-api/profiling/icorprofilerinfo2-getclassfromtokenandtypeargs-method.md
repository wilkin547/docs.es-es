---
description: 'Más información acerca de: ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs ((método)'
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 810445d2617beff55e00df6bb30130d81c740ba4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760512"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)

Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los `ClassID` valores de cualquier argumento de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleID`  
 de IDENTIFICADOR del módulo en el que reside el tipo.  
  
 `typeDef`  
 de `mdTypeDef` Token de metadatos que hace referencia al tipo.  
  
 `cTypeArgs`  
 de El número de parámetros de tipo para el tipo especificado. Este valor debe ser cero para los tipos no genéricos.  
  
 `typeArgs`  
 de Matriz de `ClassID` valores, cada uno de los cuales es un argumento del tipo. El valor de `typeArgs` puede ser null si `cTypeArgs` está establecido en cero.  
  
 `pClassID`  
 enuncia Puntero al `ClassID` del tipo especificado.  
  
## <a name="remarks"></a>Observaciones  

 La llamada al `GetClassFromTokenAndTypeArgs` método con un `mdTypeRef` token en lugar de `mdTypeDef` metadatos puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` en un `mdTypeDef` cuando lo pasen.  
  
 Si el tipo todavía no está cargado, al llamar a `GetClassFromTokenAndTypeArgs` se desencadenará la carga, que es una operación peligrosa en muchos contextos. Por ejemplo, si se llama a este método durante la carga de módulos u otros tipos, podría producirse un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.  
  
 En general, `GetClassFromTokenAndTypeArgs` no se recomienda el uso de. Si los perfiles están interesados en eventos de un tipo determinado, deben almacenar `ModuleID` y `mdTypeDef` de ese tipo, y usar [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un determinado `ClassID` es el del tipo deseado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)

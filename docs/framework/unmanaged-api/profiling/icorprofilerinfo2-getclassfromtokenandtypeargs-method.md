---
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
ms.openlocfilehash: 702c5f9f2bc08c824bdc0607741a6afd65a3e89b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497262"
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
 de `mdTypeDef`Token de metadatos que hace referencia al tipo.  
  
 `cTypeArgs`  
 de El número de parámetros de tipo para el tipo especificado. Este valor debe ser cero para los tipos no genéricos.  
  
 `typeArgs`  
 de Matriz de `ClassID` valores, cada uno de los cuales es un argumento del tipo. El valor de `typeArgs` puede ser null si `cTypeArgs` está establecido en cero.  
  
 `pClassID`  
 enuncia Puntero al `ClassID` del tipo especificado.  
  
## <a name="remarks"></a>Comentarios  
 La llamada al `GetClassFromTokenAndTypeArgs` método con un `mdTypeRef` token en lugar de `mdTypeDef` metadatos puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` en un `mdTypeDef` cuando lo pasen.  
  
 Si el tipo todavía no está cargado, al llamar a `GetClassFromTokenAndTypeArgs` se desencadenará la carga, que es una operación peligrosa en muchos contextos. Por ejemplo, si se llama a este método durante la carga de módulos u otros tipos, podría producirse un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.  
  
 En general, `GetClassFromTokenAndTypeArgs` no se recomienda el uso de. Si los perfiles están interesados en eventos de un tipo determinado, deben almacenar `ModuleID` y `mdTypeDef` de ese tipo, y usar [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un determinado `ClassID` es el del tipo deseado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)

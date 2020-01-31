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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862797"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs (Método)
Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los valores `ClassID` de cualquier argumento de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleID`  
 de IDENTIFICADOR del módulo en el que reside el tipo.  
  
 `typeDef`  
 de Un token de metadatos de `mdTypeDef` que hace referencia al tipo.  
  
 `cTypeArgs`  
 de El número de parámetros de tipo para el tipo especificado. Este valor debe ser cero para los tipos no genéricos.  
  
 `typeArgs`  
 de Matriz de valores de `ClassID`, cada uno de los cuales es un argumento del tipo. El valor de `typeArgs` puede ser NULL si `cTypeArgs` está establecido en cero.  
  
 `pClassID`  
 enuncia Puntero a la `ClassID` del tipo especificado.  
  
## <a name="remarks"></a>Notas  
 Llamar al método `GetClassFromTokenAndTypeArgs` con un `mdTypeRef` en lugar de un token de metadatos de `mdTypeDef` puede tener resultados imprevisibles; los llamadores deben resolver el `mdTypeRef` en un `mdTypeDef` al pasarlo.  
  
 Si el tipo todavía no está cargado, al llamar a `GetClassFromTokenAndTypeArgs` se desencadenará la carga, que es una operación peligrosa en muchos contextos. Por ejemplo, si se llama a este método durante la carga de módulos u otros tipos, podría producirse un bucle infinito, ya que el tiempo de ejecución intenta cargar elementos de forma circular.  
  
 En general, no se recomienda el uso de `GetClassFromTokenAndTypeArgs`. Si los perfiles están interesados en eventos de un tipo determinado, deben almacenar el `ModuleID` y `mdTypeDef` de ese tipo y usar [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) para comprobar si un `ClassID` determinado es el del tipo deseado.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)

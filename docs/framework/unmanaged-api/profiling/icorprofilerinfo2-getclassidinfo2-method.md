---
title: ICorProfilerInfo2::GetClassIDInfo2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 64d2cd76dafb1a51814b916b5ce73fb08cdcaef9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868865"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>ICorProfilerInfo2::GetClassIDInfo2 (Método)
Obtiene el módulo primario y el token de metadatos para la definición genérica abierta de la clase especificada, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `classId`  
 [in] Identificador de la clase para la que se recuperará información.  
  
 `pModuleId`  
 enuncia Puntero al identificador del módulo primario para la definición genérica abierta de la clase especificada.  
  
 `pTypeDefToken`  
 enuncia Puntero al símbolo (token) de metadatos para la definición genérica abierta de la clase especificada.  
  
 `pParentClassId`  
 [out] Puntero al identificador de la clase primaria.  
  
 `cNumTypeArgs`  
 [in] Tamaño de la matriz `typeArgs`.  
  
 `pcNumTypeArgs`  
 [out] Puntero al número total de elementos disponibles.  
  
 `typeArgs`  
 [out] Matriz de valores `ClassID`, cada uno de los cuales representa el identificador de un argumento de tipo de la clase. Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID` disponibles.  
  
## <a name="remarks"></a>Notas  
 El método `GetClassIDInfo2` es similar al método [ICorProfilerInfo:: GetClassIDInfo (](icorprofilerinfo-getclassidinfo-method.md) , pero `GetClassIDInfo2` obtiene información adicional sobre un tipo genérico.  
  
 El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de [metadatos](../../../../docs/framework/unmanaged-api/metadata/index.md) para un módulo determinado. Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.  
  
 Después de que `GetClassIDInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`. Para ello, compare el valor al que `pcNumTypeArgs` apunta con el valor del parámetro `cNumTypeArgs`. Si `pcNumTypeArgs` apunta un valor mayor que `cNumTypeArgs`, asigne un búfer `typeArgs` mayor, actualice `cNumTypeArgs` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassIDInfo2`.  
  
 También tiene la opción de llamar primero a `GetClassIDInfo2` con un búfer `typeArgs` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer `typeArgs` en el valor devuelto en `pcNumTypeArgs` y volver a llamar a `GetClassIDInfo2`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

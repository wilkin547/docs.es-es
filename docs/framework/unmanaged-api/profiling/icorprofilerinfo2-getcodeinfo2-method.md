---
title: ICorProfilerInfo2::GetCodeInfo2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
ms.openlocfilehash: 9295ea8b22f72529f55cbe13f6a79a0aa34d2fa0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868801"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a>ICorProfilerInfo2::GetCodeInfo2 (Método)
Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionID`  
 [in] Identificador de función con la que está asociado el código nativo.  
  
 `cCodeInfos`  
 [in] Tamaño de la matriz `codeInfos`.  
  
 `pcCodeInfos`  
 enuncia Puntero al número total de estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibles.  
  
 `codeInfos`  
 [out] Búfer proporcionado por el llamador. Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.  
  
## <a name="remarks"></a>Notas  
 Las extensiones se clasifican por orden de desplazamiento creciente del lenguaje intermedio de Microsoft (MSIL).  
  
 Después de la devolución de `GetCodeInfo2`, debe comprobar que el búfer `codeInfos` era lo suficientemente grande como para contener todas las estructuras `COR_PRF_CODE_INFO`. Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`. Si `cCodeInfos` dividido entre el tamaño de una estructura `COR_PRF_CODE_INFO` es menor que `pcCodeInfos`, asigne un búfer `codeInfos` mayor, actualice `cCodeInfos` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetCodeInfo2`.  
  
 También tiene la opción de llamar primero a `GetCodeInfo2` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto. A continuación, puede establecer el tamaño del búfer `codeInfos` para el valor devuelto en `pcCodeInfos` multiplicándolo por el tamaño de una estructura `COR_PRF_CODE_INFO` y volver a llamar a `GetCodeInfo2`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetCodeInfo3 (método)](icorprofilerinfo4-getcodeinfo3-method.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

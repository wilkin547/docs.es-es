---
title: ICorProfilerInfo2::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
ms.openlocfilehash: ac35b18ce8c45c95bb2fb8e820423470ca1b75bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497158"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a>ICorProfilerInfo2::GetClassLayout (Método)
Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada. Es decir, este método obtiene los desplazamientos de los campos de la clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classID`  
 [in] Identificador de la clase para la cual se recuperará la distribución.  
  
 `rFieldOffset`  
 [in, out] Matriz de estructuras de [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) , cada una de las cuales contiene los tokens y desplazamientos de los campos de la clase.  
  
 `cFieldOffset`  
 [in] Tamaño de la matriz `rFieldOffset`.  
  
 `pcFieldOffset`  
 [out] Puntero al número total de elementos disponibles. Si `cFieldOffset` es 0, este valor indica el número de elementos necesario.  
  
 `pulClassSize`  
 [out] Puntero a una ubicación que contiene el tamaño, en bytes, de la clase.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetClassLayout` solo devuelve los campos definidos por la propia clase. Si la clase primaria de la clase también tiene campos definidos, el generador de perfiles debe llamar a `GetClassLayout` en la clase primaria para obtener dichos campos.  
  
 Si usa `GetClassLayout` con clases de cadena, el método producirá un error con el código E_INVALIDARG. Use [ICorProfilerInfo2:: GetStringLayout (](icorprofilerinfo2-getstringlayout-method.md) para obtener información sobre el diseño de una cadena. `GetClassLayout` también producirá un error cuando se le llama con una clase de matriz.  
  
 Después de que `GetClassLayout` vuelva, debe comprobar que el búfer `rFieldOffset` era lo suficientemente grande como para contener todas las estructuras `COR_FIELD_OFFSET` disponibles. Para ello, compare el valor al que `pcFieldOffset` apunta con el tamaño de `rFieldOffset` dividido por el tamaño de una estructura `COR_FIELD_OFFSET`. Si `rFieldOffset` no es suficientemente grande, asigne un búfer `rFieldOffset` mayor, actualice `cFieldOffset` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetClassLayout`.  
  
 También tiene la opción de llamar primero a `GetClassLayout` con un búfer `rFieldOffset` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcFieldOffset` y volver a llamar a `GetClassLayout`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

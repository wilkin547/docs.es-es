---
description: 'Más información acerca de: ICorProfilerInfo:: Getmoduleinfo ((método)'
title: ICorProfilerInfo::GetModuleInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: 003f40e6637490be23e8bf87a6bac8ab76bc50e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647200"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a>ICorProfilerInfo::GetModuleInfo (Método)

A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 [in] Identificador del módulo para el que se recuperará la información.  
  
 `ppBaseLoadAddress`  
 [out] Dirección base en la que se carga el módulo.  
  
 `cchName`  
 [in] Longitud, en caracteres, del búfer de retorno `szName`.  
  
 `pcchName`  
 [out] Puntero a la longitud total de caracteres del nombre de archivo del módulo que se devuelve.  
  
 `szName`  
 [out] Búfer de caracteres anchos proporcionado por el llamador. Cuando el método vuelve, este búfer contiene el nombre de archivo del módulo.  
  
 `pAssemblyId`  
 [out] Puntero al identificador del ensamblado primario del módulo.  
  
## <a name="remarks"></a>Observaciones  

 Para los módulos dinámicos, el parámetro `szName` es una cadena vacía y la dirección base es 0 (cero).  
  
 Aunque `GetModuleInfo` se puede llamar al método en cuanto existe el identificador del módulo, el identificador del ensamblado primario no estará disponible hasta que el generador de perfiles reciba la devolución de llamada [ICorProfilerCallback:: moduleattachedtoassembly (](icorprofilercallback-moduleattachedtoassembly-method.md) .  
  
 Cuando `GetModuleInfo` vuelve, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre de archivo completo del módulo. Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`. Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetModuleInfo`.  
  
 También tiene la opción de llamar primero a `GetModuleInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetModuleInfo`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
- [Método GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)

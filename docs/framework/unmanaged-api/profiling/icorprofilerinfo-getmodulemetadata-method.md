---
title: ICorProfilerInfo::GetModuleMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 74df0fb412e7fb3d9f779391ec84f07a0379a2cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724122"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData (Método)

Obtiene una instancia de la interfaz de metadatos que se asigna al módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 de IDENTIFICADOR del módulo al que se asignará la instancia de interfaz.  
  
 `dwOpenFlags`  
 de Un valor de la enumeración [CorOpenFlags (](../metadata/coropenflags-enumeration.md) que especifica el modo para abrir los archivos de manifiesto. Solo los `ofRead` `ofWrite` bits, y `ofNoTransform` son válidos.  
  
 `riid`  
 de IDENTIFICADOR de referencia (GUID) de la interfaz de metadatos cuya instancia se va a recuperar. Vea [interfaces de metadatos](../metadata/metadata-interfaces.md) para obtener una lista de las interfaces.  
  
 `ppOut`  
 enuncia Puntero a la dirección de la instancia de la interfaz de metadatos.  
  
## <a name="remarks"></a>Comentarios  

 Puede solicitar que los metadatos se abran en modo de lectura/escritura, pero esto hará que la ejecución del programa sea más lenta, ya que los cambios realizados en los metadatos no se pueden optimizar tal como estaban del compilador.  
  
 Algunos módulos (como los módulos de recursos) no tienen metadatos. En esos casos, `GetModuleMetaData` devolverá un valor HRESULT de S_FALSE y un valor null en * `ppOut` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)

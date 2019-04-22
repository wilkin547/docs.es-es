---
title: ICorProfilerInfo::GetCodeInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d069446ecb0b630870f0d2c9c4bdc23232c40c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120697"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>ICorProfilerInfo::GetCodeInfo (Método)
Obtiene la extensión del código nativo asociado al identificador de función especificado.  
  
 Este método está obsoleto. Use la [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] Identificador de función con la que está asociado el código nativo.  
  
 `pStart`  
 [out] Puntero a una matriz de bytes que compone el código nativo de la función.  
  
 `pcSize`  
 [out] Puntero a un entero que especifica el tamaño, en bytes, del código nativo.  
  
## <a name="remarks"></a>Comentarios  
 Para optimizar el rendimiento, el tiempo de ejecución en la versión 2.0 de .NET Framework divide el código nativo precompilado de una función en varias regiones. Por consiguiente, el método `GetCodeInfo` está obsoleto en .NET Framework 2.0 porque no puede controlar la cantidad de código nativo de una función. Los generadores de perfiles deben usar en su lugar el método `ICorProfilerInfo2::GetCodeInfo2`, que es más general.  
  
 Esta función usa búferes asignados por el llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.0  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

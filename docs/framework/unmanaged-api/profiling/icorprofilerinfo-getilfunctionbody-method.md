---
title: ICorProfilerInfo::GetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: 8160bb5b9ca5e0a4e22a1a831e978eaf125e7605
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870497"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody (Método)
Obtiene un puntero al cuerpo de un método en el código del lenguaje intermedio de Microsoft (MSIL), comenzando en su encabezado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleId`  
 de IDENTIFICADOR del módulo en el que reside la función.  
  
 `methodId`  
 de Símbolo (token) de metadatos para el método.  
  
 `ppMethodHeader`  
 enuncia Puntero al encabezado del método.  
  
 `pcbMethodSize`  
 enuncia Entero que especifica el tamaño del método.  
  
## <a name="remarks"></a>Notas  
 Un método está en el ámbito del módulo en el que reside. Dado que el método `GetILFunctionBody` está diseñado para proporcionar a una herramienta acceso al código MSIL antes de que lo haya cargado el Common Language Runtime (CLR), utiliza el token de metadatos del método para buscar la instancia deseada.  
  
 `GetILFunctionBody` puede devolver un CORPROF_E_FUNCTION_NOT_IL HRESULT si el `methodId` apunta a un método sin código MSIL (como un método abstracto o un método de invocación de plataforma (PInvoke)).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)

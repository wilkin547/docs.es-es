---
title: ICorProfilerInfo::SetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d10bb7033688efce9488078d2ef605e2a29382f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792658"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody (Método)
Reemplaza el cuerpo de la función especificada en el módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo en el que reside la función.  
  
 `methodid`  
 [in] El token de la función que se va a reemplazar el cuerpo.  
  
 `pbNewILMethodHeader`  
 [in] El nuevo encabezado para la función.  
  
## <a name="remarks"></a>Comentarios  
 El `SetILFunctionBody` método reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al cuerpo de la nueva función y ajusta las estructuras internas de datos según sea necesario.  
  
 El `SetILFunctionBody` método puede llamarse en sólo aquellas funciones que nunca se han compilado mediante un compilador just-in-time (JIT).  
  
 Use la [GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) método para asignar espacio para el nuevo método para asegurarse de que el búfer es compatible.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

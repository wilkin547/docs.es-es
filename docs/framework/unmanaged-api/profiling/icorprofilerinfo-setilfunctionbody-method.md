---
title: "ICorProfilerInfo::SetILFunctionBody (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6d97827555ecefb775323fdf9dbd6577f941f1e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo en el que reside la función.  
  
 `methodid`  
 [in] El token de la función para la que se va a reemplazar el cuerpo.  
  
 `pbNewILMethodHeader`  
 [in] El nuevo encabezado de la función.  
  
## <a name="remarks"></a>Comentarios  
 El `SetILFunctionBody` método reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de función y ajusta las estructuras de datos internas según sea necesario.  
  
 El `SetILFunctionBody` método puede llamarse en sólo aquellas funciones que nunca se han compilado mediante un compilador just-in-time (JIT).  
  
 Use la [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) método para asignar espacio para el nuevo método para asegurarse de que el búfer es compatible.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

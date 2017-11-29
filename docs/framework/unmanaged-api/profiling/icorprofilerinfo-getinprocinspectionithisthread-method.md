---
title: "ICorProfilerInfo::GetInprocInspectionIThisThread (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionIThisThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9a260143e36939f4201d7949f5783f80e5c20ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>ICorProfilerInfo::GetInprocInspectionIThisThread (Método)
Obtiene un objeto que se pueden consultar para ICorDebugThread (interfaz). Este método está obsoleto en la versión 2.0 de .NET Framework.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppicd`  
 [out](/cpp/atl/iunknown) objeto que se puede consultar para el `ICorDebugThread` interfaz.  
  
## <a name="remarks"></a>Comentarios  
 Los servicios de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework. Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso. Como resultado de los comentarios de clientes, la depuración en proceso tiene ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en línea con la API de generación de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versión de .NET framework:** 1.0  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

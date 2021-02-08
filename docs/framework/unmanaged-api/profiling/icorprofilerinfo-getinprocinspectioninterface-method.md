---
description: 'Más información acerca de: ICorProfilerInfo:: GetInprocInspectionInterface ((método)'
title: ICorProfilerInfo::GetInprocInspectionInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: 5b7ce053f0a64afd5d702a4eb59c1712f4b26e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781472"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a>ICorProfilerInfo::GetInprocInspectionInterface (Método)

Obtiene un objeto que se puede consultar para una interfaz "ICorDebugProcess". Este método está obsoleto en la .NET Framework versión 2,0.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppicd`  
 objeto [out](/cpp/atl/iunknown) que se puede consultar para una `ICorDebugProcess` interfaz.  
  
## <a name="remarks"></a>Observaciones  

 La API de depuración de Common Language Runtime (CLR) admite la depuración limitada en proceso en la .NET Framework versión 1,0. La depuración en proceso ha habilitado un generador de perfiles para usar las partes de inspección de la API de depuración. Como resultado de los comentarios de los clientes, la depuración en proceso se ha quitado del .NET Framework en la versión 2,0 y se ha reemplazado por un conjunto de funcionalidades que está más en línea con la API de generación de perfiles.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versión de .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)

---
description: 'Más información acerca de: ICorProfilerInfo:: SetILFunctionBody ((método)'
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
ms.openlocfilehash: 38e7907080065dc96d72a3d38a67227414637a70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647172"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody (Método)

Reemplaza el cuerpo de la función especificada en el módulo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 de IDENTIFICADOR del módulo en el que reside la función.  
  
 `methodid`  
 de Token de la función para la que se va a reemplazar el cuerpo.  
  
 `pbNewILMethodHeader`  
 de Nuevo encabezado de la función.  
  
## <a name="remarks"></a>Observaciones  

 El `SetILFunctionBody` método reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de la función y ajusta las estructuras de datos internas según sea necesario.  
  
 `SetILFunctionBody`Solo se puede llamar al método en aquellas funciones que nunca ha compilado un compilador Just-in-Time (JIT).  
  
 Use el método [ICorProfilerInfo:: getilfunctionbodyallocator (](icorprofilerinfo-getilfunctionbodyallocator-method.md) para asignar espacio para el nuevo método con el fin de asegurarse de que el búfer sea compatible.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)

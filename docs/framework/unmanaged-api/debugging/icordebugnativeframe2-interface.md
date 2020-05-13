---
title: ICorDebugNativeFrame2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: cd2a2821128ad9265e8a831f7b02792e6453b1ee
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213795"
---
# <a name="icordebugnativeframe2-interface"></a>ICorDebugNativeFrame2 (Interfaz)
Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método IsChild](icordebugnativeframe2-ischild-method.md)|Determina si el marco actual es un marco secundario.|  
|[Método IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md)|Determina si el marco especificado es el elemento primario del marco actual.|  
|[Método GetStackParameterSize](icordebugnativeframe2-getstackparametersize-method.md)|Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.|  
  
## <a name="remarks"></a>Observaciones  
 Esta interfaz extiende lógicamente la interfaz "ICorDebugNativeFrame".  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

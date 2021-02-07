---
description: 'Más información acerca de: interfaz ICorDebugNativeFrame2'
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
ms.openlocfilehash: 9ed0e20bb29bef3b210258956ebecb1ee7a96df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722352"
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
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

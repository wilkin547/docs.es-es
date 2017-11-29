---
title: "ICorDebugController::Detach (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Detach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d8c1df2fd2aa52f9f5e90a27d42f6568686e908
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerdetach-method"></a>ICorDebugController::Detach (Método)
Desasocia al depurador desde el proceso o dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Comentarios  
 El proceso o dominio de aplicación continúa la ejecución con normalidad, pero el objeto "ICorDebugProcess" o "ICorDebugAppDomain" ya no es válido y no se producirán ningún más devoluciones de llamada.  
  
 En la versión 2.0 de .NET Framework, si está habilitada la depuración no administrada, este método se producirá un error debido a limitaciones del sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 

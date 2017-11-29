---
title: ICorDebugStringValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue
helpviewer_keywords: ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03ae6fba5d880b11baac695866853e0b3a4d8cc7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvalue-interface1"></a>ICorDebugStringValue Interfaz1
Una subclase de ICorDebugHeapValue que se aplica a valores de cadena.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetLength (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|Obtiene el número de caracteres de la cadena que hace referencia esta `ICorDebugStringValue`.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|Obtiene la cadena que hace referencia esta `ICorDebugStringValue`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

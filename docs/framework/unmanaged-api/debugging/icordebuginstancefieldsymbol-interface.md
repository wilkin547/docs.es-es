---
title: ICorDebugInstanceFieldSymbol (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbf3f07f5669c4fcafa4d3cc4119fc715539651d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbol-interface"></a>ICorDebugInstanceFieldSymbol (Interfaz)
Representa la información de símbolos de depuración para un campo de instancia.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|Obtiene el nombre del campo de instancia.|  
|[GetOffset (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|Obtiene el tamaño, en bytes, del campo de instancia.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.  
  
> [!NOTE]
>  Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugStaticFieldSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

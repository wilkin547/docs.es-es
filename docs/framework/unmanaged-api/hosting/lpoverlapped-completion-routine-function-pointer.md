---
title: "puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b1846cf8fff5c41fc54ddeec5b495b50c63581c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE
Señala a una función que notifica al host cuándo una superposición (es decir, asincrónica) ha completado la E/S en un dispositivo.  
  
 Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwErrorCode`  
 [in] Un valor que es un código de error si se ha cerrado el dispositivo; en caso contrario, este valor es cero.  
  
 Cerrar un dispositivo, se produce todas pendientes de E/S en el dispositivo para completar de forma inmediata.  
  
 `dwNumberOfBytesTransfered`  
 [in] El número de bytes transferidos por la operación de E/S.  
  
 `lpOverlapped`  
 [in] Un puntero a una estructura que contiene información que se utilizará para completar la solicitud de E/S.  
  
## <a name="remarks"></a>Comentarios  
 La función a la que `LPOVERLAPPED_COMPLETION_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación host. La función de devolución de llamada permite al host procesar la solicitud de E/S completada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorWks.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

---
title: puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce2ce6dd1210eef94e77b5d6a2d58a35cf971e6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138780"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE
Señala a una función que notifica al host cuándo una superpuesta (es decir, asincrónica) se ha completado la E/S en un dispositivo.  
  
 Este puntero de función ha quedado obsoleto en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwErrorCode`  
 [in] Un valor que es un código de error si el dispositivo se ha cerrado; en caso contrario, este valor es cero.  
  
 Cerrar un dispositivo hace que todas las pendientes de E/S en el dispositivo para completarse inmediatamente.  
  
 `dwNumberOfBytesTransfered`  
 [in] El número de bytes transferidos por la operación de E/S.  
  
 `lpOverlapped`  
 [in] Un puntero a una estructura que contiene información que se utilizará para completar la solicitud de E/S.  
  
## <a name="remarks"></a>Comentarios  
 La función a la que `LPOVERLAPPED_COMPLETION_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación de hospedaje. La función de devolución de llamada permite al host procesar la solicitud de E/S completada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorWks.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

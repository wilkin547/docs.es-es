---
title: CorExitProcess (Función)
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b95625cfe17b36c0244e6780a08dcf50ce50763d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985821"
---
# <a name="corexitprocess-function"></a>CorExitProcess (Función)
Se cierra el proceso no administrado actual.  
  
 Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Use la [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `exitCode`  
 Un entero que especifica el código de salida.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  A partir del [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` se cierra cada runtime iniciado en el proceso, no solo el tiempo de ejecución a la que se han enlazado las API heredadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

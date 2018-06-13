---
title: GetStartupNotificationEvent (Función)
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3692471e0652a1a812b1d0cbed9e38cc32112ef4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404315"
---
# <a name="getstartupnotificationevent-function"></a>GetStartupNotificationEvent (Función)
Crea o abre un identificador de evento al que señalará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `debuggeePID`  
 [in] Identificador de proceso del proceso de destino desde el que se reciben las notificaciones de inicio del CLR.  
  
 `phStartupEvent`  
 [out] Puntero a un identificador que señalará un CLR en el inicio.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 El identificador del evento de notificación de inicio se obtuvo correctamente.  
  
 E_INVALIDARG  
 `phStartupEvent` es nulo o `debuggeePID` no hace referencia a un proceso actualmente en ejecución.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede obtener el identificador del evento de notificación de inicio.  
  
## <a name="remarks"></a>Comentarios  
 En el sistema operativo Windows, `debuggeePID` se asigna a un identificador de proceso del sistema operativo.  
  
 El evento se señala antes de que el CLR que lo señaló ejecute ningún código administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim.h  
  
 **Biblioteca:** dbgshim.dll  
  
 **Versiones de .NET framework:** 3.5 SP1

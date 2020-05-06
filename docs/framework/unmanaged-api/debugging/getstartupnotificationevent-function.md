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
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860716"
---
# <a name="getstartupnotificationevent-function"></a>GetStartupNotificationEvent (Función)
Crea o abre un identificador de evento al que apuntará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Parámetros  
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
 En el sistema operativo Windows, `debuggeePID` se asigna a un identificador de procesos del sistema operativo.  
  
 El evento se señala antes de que el CLR que lo señaló ejecute ningún código administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim. dll  
  
 **.NET Framework versiones:** 3,5 SP1

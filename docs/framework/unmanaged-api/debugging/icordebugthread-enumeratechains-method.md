---
title: ICorDebugThread::EnumerateChains (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482865"
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains (Método)
Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppChains`  
 [out] Un puntero a la dirección de un `ICorDebugChainEnum` objeto que permite la enumeración de la pila de todos los encadena en este subproceso, empezando por la cadena activa (es decir, la más reciente).  
  
## <a name="remarks"></a>Comentarios  
 La cadena de pila representa la pila de llamadas física del subproceso. Las circunstancias siguientes crean un límite de la cadena de pila:  
  
-   Una transición de administrado a no administrado o no administrado a administrado.  
  
-   Un cambio de contexto.  
  
-   Un secuestro de un subproceso de usuario del depurador.  
  
 En el caso de un subproceso que se ejecuta exclusivamente código administrado en un contexto único, una correspondencia uno a uno existirá entre los subprocesos y las cadenas de la pila.  
  
 Un depurador que desee reorganizar las pilas de llamadas física de todos los subprocesos en pilas de llamadas lógicas. Esto implicaría ordenar las cadenas de todos los subprocesos por sus relaciones de llamador y destinatario y reagrupar ellos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

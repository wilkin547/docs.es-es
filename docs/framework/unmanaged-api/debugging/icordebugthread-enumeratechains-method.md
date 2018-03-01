---
title: "ICorDebugThread::EnumerateChains (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains (Método)
Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppChains`  
 [out] Un puntero a la dirección de un `ICorDebugChainEnum` vincula el objeto que permite la enumeración de todos los del pila en este subproceso, empezando por la cadena de activo (es decir, la más reciente).  
  
## <a name="remarks"></a>Comentarios  
 La cadena de pila representa la pila de llamadas física del subproceso. Las circunstancias siguientes crean un límite de la cadena de pila:  
  
-   Una transición a administrado o no administrado a administrado.  
  
-   Un cambio de contexto.  
  
-   Un secuestro de un subproceso de usuario del depurador.  
  
 En un caso simple para un subproceso que se ejecuta exclusivamente código administrado en un único contexto, existirá una correspondencia uno a uno entre los subprocesos y cadenas de la pila.  
  
 Un depurador que desee reorganizar las pilas de llamadas física de todos los subprocesos en pilas de llamada lógico. Esto incluiría la ordenación de cadenas de todos los subprocesos por sus relaciones de llamador/destinatario y reagrupar ellos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

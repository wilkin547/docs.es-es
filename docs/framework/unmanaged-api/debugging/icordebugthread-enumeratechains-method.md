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
ms.openlocfilehash: 38fe50f5a6608bb27d7a7818dee4784a7f8113ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133604"
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains (Método)
Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppChains`  
 enuncia Puntero a la dirección de un objeto `ICorDebugChainEnum` que permite la enumeración de todas las cadenas de pila de este subproceso, comenzando en la cadena activa (es decir, la más reciente).  
  
## <a name="remarks"></a>Comentarios  
 La cadena de pila representa la pila de llamadas física del subproceso. Las siguientes circunstancias crean un límite de cadena de pila:  
  
- Una transición administrada a no administrada o no administrada.  
  
- Un cambio de contexto.  
  
- Un depurador que secuestra un subproceso de usuario.  
  
 En el caso simple de un subproceso que ejecuta código meramente administrado en un contexto único, existirá una correspondencia uno a uno entre los subprocesos y las cadenas de pila.  
  
 Es posible que un depurador desee reorganizar las pilas de llamadas físicas de todos los subprocesos en pilas de llamadas lógicas. Esto implicaría ordenar todas las cadenas de subprocesos por sus relaciones llamador y destinatario y reagruparlas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

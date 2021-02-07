---
description: 'Más información acerca de: ICorDebugAssembly:: GetProcess (método)'
title: ICorDebugAssembly::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: b121d7f892f6e2e2aa76290d4aee51767c72e9fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754156"
---
# <a name="icordebugassemblygetprocess-method"></a>ICorDebugAssembly::GetProcess (Método)

Obtiene un puntero de interfaz al proceso en el que se está ejecutando esta instancia de ICorDebugAssembly.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppProcess`  
 enuncia Puntero a una interfaz ICorDebugProcess que representa el proceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

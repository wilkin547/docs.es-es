---
title: ICorDebugModule::GetAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78bfc91bdd0f9fa68252c6a07e1362807eb507b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416028"
---
# <a name="icordebugmodulegetassembly-method"></a>ICorDebugModule::GetAssembly (Método)
Obtiene el ensamblado que contiene este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppAssembly`  
 [out] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado que contiene este módulo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

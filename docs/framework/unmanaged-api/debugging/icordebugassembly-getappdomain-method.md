---
title: ICorDebugAssembly::GetAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ba09b80d7118b0ccd9b1647011a7fc7cd74e22
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485114"
---
# <a name="icordebugassemblygetappdomain-method"></a>ICorDebugAssembly::GetAppDomain (Método)
Obtiene un puntero de interfaz al dominio de aplicación que contiene esta `ICorDebugAssembly` instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppAppDomain`  
 [out] Un puntero a la dirección de una interfaz ICorDebugAppDomain que representa el dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 Si este ensamblado es el ensamblado del sistema, `GetAppDomain` devuelve null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

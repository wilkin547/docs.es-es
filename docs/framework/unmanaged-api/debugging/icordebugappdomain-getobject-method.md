---
title: ICorDebugAppDomain::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737844"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject (Método)
Obtiene un puntero de interfaz para el dominio de aplicación de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppObject`  
 [out] Un puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.  
  
## <a name="return-value"></a>Valor devuelto  
 Si un administrado <xref:System.AppDomain?displayProperty=nameWithType> aún no ha construido el objeto para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject`.  
  
## <a name="remarks"></a>Comentarios  
 Cada dominio de aplicación en un proceso puede tener un administrado <xref:System.AppDomain?displayProperty=nameWithType> objeto en el tiempo de ejecución que lo representa. Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este administrados <xref:System.AppDomain?displayProperty=nameWithType> objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

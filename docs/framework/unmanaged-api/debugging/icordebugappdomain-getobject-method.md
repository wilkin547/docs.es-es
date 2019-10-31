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
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134714"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject (Método)
Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppObject`  
 enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el dominio de aplicación CLR.  
  
## <a name="return-value"></a>Valor devuelto  
 Si no se ha construido un objeto de <xref:System.AppDomain?displayProperty=nameWithType> administrado para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject`.  
  
## <a name="remarks"></a>Comentarios  
 Cada dominio de aplicación de un proceso puede tener un objeto <xref:System.AppDomain?displayProperty=nameWithType> administrado en el tiempo de ejecución que lo representa. Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este objeto <xref:System.AppDomain?displayProperty=nameWithType> administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

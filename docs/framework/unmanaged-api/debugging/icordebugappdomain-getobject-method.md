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
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676067"
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

 Si no <xref:System.AppDomain?displayProperty=nameWithType> se ha construido un objeto administrado para este dominio de aplicación, el método devuelve `S_FALSE` y coloca `NULL` en `*ppObject` .  
  
## <a name="remarks"></a>Comentarios  

 Cada dominio de aplicación de un proceso puede tener un <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado en tiempo de ejecución que lo representa. Esta función obtiene un objeto de interfaz ICorDebugValue que corresponde a este <xref:System.AppDomain?displayProperty=nameWithType> objeto administrado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

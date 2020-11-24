---
title: ICorDebugAppDomain::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 501a4543940437bfe2a6cb0952aed8184107150c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672167"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName (Método)

Obtiene el nombre del dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchName`  
 [in] Tamaño de la matriz `szName`. Establezca este valor en cero para poner este método en modo de consulta.  
  
 `pcchName`  
 enuncia Puntero al tamaño del nombre o número de caracteres devueltos realmente en `szName` . En el modo de consulta, este valor permite que el autor de la llamada sepa el tamaño de un búfer que se va a asignar al nombre.  
  
 `szName`  
 enuncia Matriz que almacena el nombre del dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  

 Un depurador llama al `GetName` método una vez para obtener el tamaño de un búfer necesario para el nombre. El depurador asigna el búfer y, a continuación, llama al método una segunda vez para rellenar el búfer. La primera llamada, para obtener el tamaño del nombre, se conoce como modo de *consulta*.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

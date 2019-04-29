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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7939f7b1c0c725bb4e8c642bc38121dd755da5e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785143"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName (Método)
Obtiene el nombre del dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [out] Un puntero al tamaño del nombre o el número de caracteres devueltos realmente en `szName`. En el modo de consulta, este valor permite al llamador saber el tamaño del búfer para asignar el nombre.  
  
 `szName`  
 [out] Una matriz que almacena el nombre del dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 Llama un depurador el `GetName` método una vez para obtener el tamaño de un búfer necesario para el nombre. El depurador asigna el búfer y, a continuación, llama al método una segunda vez para llenar el búfer. La primera llamada, para obtener el tamaño del nombre, se conoce como *el modo de consulta*.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

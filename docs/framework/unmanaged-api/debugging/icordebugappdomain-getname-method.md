---
title: "ICorDebugAppDomain::GetName (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62defcb4b7a2f143269c7f617b762e3419d55426
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] Tamaño de la matriz `szName`. Establezca este valor en cero para poner este método en modo de consulta.  
  
 `pcchName`  
 [out] Un puntero al tamaño del nombre o el número de caracteres devueltos realmente en `szName`. En el modo de consulta, este valor permite al llamador saber el tamaño del búfer para asignar el nombre.  
  
 `szName`  
 [out] Una matriz que almacena el nombre del dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 Llama a un depurador el `GetName` una vez al método para obtener el tamaño de un búfer necesario para el nombre. El depurador asigna el búfer y, a continuación, llama al método una segunda vez para llenar el búfer. La primera llamada, para obtener el tamaño del nombre, se conoce como *el modo de consulta*.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

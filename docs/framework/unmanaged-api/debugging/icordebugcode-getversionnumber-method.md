---
title: ICorDebugCode::GetVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 155a8d5465e0fb19c55c9d11b67c6031c2b2c4a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747517"
---
# <a name="icordebugcodegetversionnumber-method"></a>ICorDebugCode::GetVersionNumber (Método)
Obtiene el número basado en uno que identifica la versión del código que representa esta "ICorDebugCode".  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nVersion`  
 [out] Un puntero al número de versión del código.  
  
## <a name="remarks"></a>Comentarios  
 El número de versión se incrementa cada vez que un editar y continuar (EnC) se realiza en el código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

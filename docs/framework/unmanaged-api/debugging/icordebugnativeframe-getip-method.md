---
title: ICorDebugNativeFrame::GetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d17ac4230296674381c87851377fcb535837ad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416824"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP (Método)
Obtiene el código nativo desplaza ubicación a la que está establecido actualmente el puntero de instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pnOffset`  
 [out] Un puntero a la ubicación de desplazamiento en el código nativo.  
  
## <a name="remarks"></a>Comentarios  
 Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecutará. Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se ejecuta cuando se reactiva el marco de pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 

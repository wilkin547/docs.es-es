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
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213600"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP (Método)
Obtiene la ubicación de desplazamiento del código nativo en la que está establecido actualmente el puntero de instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnOffset`  
 enuncia Puntero a la ubicación de desplazamiento en el código nativo.  
  
## <a name="remarks"></a>Observaciones  
 Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar. Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar cuando se reactive el marco de pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

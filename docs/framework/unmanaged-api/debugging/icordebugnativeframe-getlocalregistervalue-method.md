---
title: ICorDebugNativeFrame::GetLocalRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
ms.openlocfilehash: 132e0868426670ba61d8ee12ba7007be1a8a52de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139396"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterValue (Método)
Obtiene el valor de un argumento o una variable local que se almacena en el registro especificado para este marco nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `reg`  
 de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene el valor.  
  
 `cbSigBlob`  
 de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el parámetro `pvSigBlob`.  
  
 `pvSigBlob`  
 de Un valor `PCCOR_SIGNATURE` que apunta a la firma de metadatos binarios del tipo del valor.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro especificado.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetLocalRegisterValue` se puede utilizar en un marco nativo o en un marco compilado Just-in-Time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: a45061b6a3105565fdbb36173731b3c3dfe5aa4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137289"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)
Obtiene el valor de un argumento o una variable local que se almacena en los dos registros especificados para este marco nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `highWordReg`  
 de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra alta del valor.  
  
 `lowWordReg`  
 de Un valor de la enumeración `CorDebugRegister` que especifica el registro que contiene la palabra baja del valor.  
  
 `cbSigBlob`  
 de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el parámetro `pvSigBlob`.  
  
 `pvSigBlob`  
 de Un valor `PCCOR_SIGNATURE` que apunta a la firma de metadatos binarios del tipo del valor.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetLocalDoubleRegisterValue` se puede utilizar en un marco nativo o en un marco compilado Just-in-Time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

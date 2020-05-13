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
ms.openlocfilehash: 21c4d00e4156b9db27ae4188aace19764a2be53e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213080"
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
 de Un valor de la `CorDebugRegister` enumeración que especifica el registro que contiene la palabra baja del valor.  
  
 `cbSigBlob`  
 de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.  
  
 `pvSigBlob`  
 de `PCCOR_SIGNATURE`Valor que apunta a la firma de metadatos binarios del tipo del valor.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.  
  
## <a name="remarks"></a>Observaciones  
 El `GetLocalDoubleRegisterValue` método se puede utilizar en un marco nativo o en un marco compilado Just-in-Time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

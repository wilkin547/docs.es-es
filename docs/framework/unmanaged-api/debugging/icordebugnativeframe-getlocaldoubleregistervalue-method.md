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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9de77f942a1b89b0ab11ef71229e491a5305cafc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420757"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)
Obtiene el valor de un argumento o una variable local que se almacena en los dos registros especificados para este marco nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `highWordReg`  
 [in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene los bytes más significativos del valor.  
  
 `lowWordReg`  
 [in] Un valor de la `CorDebugRegister` enumeración que especifica el registro que contiene los bytes menos significativos del valor.  
  
 `cbSigBlob`  
 [in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.  
  
 `pvSigBlob`  
 [in] Un `PCCOR_SIGNATURE` valor que señala a la firma de metadatos binaria del tipo de valor.  
  
 `ppValue`  
 [out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.  
  
## <a name="remarks"></a>Comentarios  
 El `GetLocalDoubleRegisterValue` método se puede utilizar en un marco nativo o un just-in-time (JIT)-marco compilado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 

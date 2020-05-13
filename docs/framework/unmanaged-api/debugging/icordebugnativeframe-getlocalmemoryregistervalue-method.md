---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: 91f0a75f127afcff89c2b92bf3ed67466b205081
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213054"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)
Obtiene el valor de un argumento o una variable local, de la que la palabra baja y la palabra alta se almacenan en el registro y la ubicación de memoria especificados, respectivamente, para este marco nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `highWordAddress`  
 de `CORDB_ADDRESS`Valor que especifica la ubicación de memoria que contiene la palabra alta del valor.  
  
 `lowWordRegister`  
 de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra baja del valor.  
  
 `cbSigBlob`  
 de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.  
  
 `pvSigBlob`  
 de `PCCOR_SIGNATURE`Valor que apunta a la firma de metadatos binarios del tipo del valor.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro y la ubicación de memoria especificados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

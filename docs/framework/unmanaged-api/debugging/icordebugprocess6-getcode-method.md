---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 94882c67752705f9f13b858ae3b386a19dc103a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178555"
---
# <a name="icordebugprocess6getcode-method"></a>Método ICorDebugProcess6::GetCode
Obtiene información sobre el código administrado en una dirección de código determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a>Parámetros  
 `codeAddress`  
 [en] Un [valor de CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que especifica la dirección inicial del segmento de código administrado.  
  
 `ppCode`  
 [fuera] Puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess6 (interfaz)](icordebugprocess6-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)

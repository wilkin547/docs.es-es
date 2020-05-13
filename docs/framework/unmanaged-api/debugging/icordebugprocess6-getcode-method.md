---
title: Método ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 178d1df7e6c8246b18afed442e944c49051b6597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209271"
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
 de Un valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que especifica la dirección de inicio del segmento de código administrado.  
  
 `ppCode`  
 enuncia Puntero a la dirección de un objeto "ICorDebugCode" que representa un segmento de código administrado.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)

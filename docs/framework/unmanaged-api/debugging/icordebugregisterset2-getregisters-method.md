---
title: ICorDebugRegisterSet2::GetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1b90390689e709ee131935bd6417fa6b273eb2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769982"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters (Método)
Obtiene el valor de cada registro (para la plataforma en la que se está ejecutando código) especificado por la máscara de bits especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `maskCount`  
 [in] El tamaño, en bytes, de la `mask` matriz.  
  
 `mask`  
 [in] Una matriz de bytes, cada bit de los cuales corresponde a un registro. Si el bit es 1, se recuperará el valor del registro correspondiente.  
  
 `regCount`  
 [in] El número de valores de registro va a recuperar.  
  
 `regBuffer`  
 [out] Una matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe el valor de un registro.  
  
## <a name="remarks"></a>Comentarios  
 El `GetRegisters` método devuelve una matriz de valores de los registros especificados por la máscara. La matriz no contiene valores de los registros cuyo bit de máscara no está establecido. Por lo tanto, el tamaño de la `regBuffer` matriz debe ser igual al número del 1 de la máscara. Si el valor de `regCount` es demasiado pequeño para el número de registros indicado por la máscara, los valores de los registros con números más alto se truncará del conjunto. Si `regCount` es demasiado grande, el sin usar `regBuffer` se modificarán los elementos.  
  
 Si un registro no disponible se indica por la máscara, se devolverá un valor indeterminado para ese registro.  
  
 El `ICorDebugRegisterSet2::GetRegisters` método es necesario para las plataformas que tienen más de 64 registros. Por ejemplo, IA64 tiene 128 registros de propósito general y 128 registros de punto flotante, por lo que necesita más de 64 bits en la máscara de bits.  
  
 Si no tiene más de 64 registros, como es el caso en plataformas como x86, el `GetRegisters` método realmente se limita a traducir los bytes en el `mask` matriz de bytes en un `ULONG64` y, a continuación, llama a la [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) método, que toma el `ULONG64` máscara.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)

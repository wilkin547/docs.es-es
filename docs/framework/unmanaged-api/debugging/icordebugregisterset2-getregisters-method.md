---
description: 'Más información sobre: ICorDebugRegisterSet2:: Getregisters ((método)'
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
ms.openlocfilehash: 58af939b0e88185e2be23b69ca70d28e93ff873f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794798"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2:: Getregisters ((método)

Obtiene el valor de cada registro (para la plataforma en la que se está ejecutando el código actualmente) especificado por la máscara de bits determinada.  
  
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
 de Tamaño, en bytes, de la `mask` matriz.  
  
 `mask`  
 de Matriz de bytes, cada bit de la que corresponde a un registro. Si el bit es 1, se recuperará el valor del registro correspondiente.  
  
 `regCount`  
 de Número de valores de registro que se van a recuperar.  
  
 `regBuffer`  
 enuncia Matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe el valor de un registro.  
  
## <a name="remarks"></a>Observaciones

 El `GetRegisters` método devuelve una matriz de valores de los registros especificados por la máscara. La matriz no contiene valores de registros cuyo bit de máscara no se ha establecido. Por lo tanto, el tamaño de la `regBuffer` matriz debe ser igual al número de 1 de la máscara. Si el valor de `regCount` es demasiado pequeño para el número de registros indicados por la máscara, los valores de los registros con mayor número se truncarán del conjunto. Si `regCount` es demasiado grande, los elementos no utilizados no se `regBuffer` modificarán.  
  
 Si la máscara indica un registro no disponible, se devolverá un valor indeterminado para ese registro.  
  
 El `ICorDebugRegisterSet2::GetRegisters` método es necesario para las plataformas que tienen más de 64 registros. Por ejemplo, IA64 tiene 128 registros de uso general y registros de punto flotante de 128, por lo que necesita más de 64 bits en la máscara de bits.  
  
 Si no tiene más de 64 registros, como sucede en plataformas como x86, el `GetRegisters` método simplemente convierte los bytes de la `mask` matriz de bytes en `ULONG64` y, a continuación, llama al método [ICorDebugRegisterSet:: getregisters (](icordebugregisterset-getregisters-method.md) , que toma la `ULONG64` máscara.  
  
## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet (Interfaz)](icordebugregisterset-interface.md)

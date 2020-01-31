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
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792057"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters (Método)
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
  
## <a name="parameters"></a>Parameters  
 `maskCount`  
 de Tamaño, en bytes, de la matriz de `mask`.  
  
 `mask`  
 de Matriz de bytes, cada bit de la que corresponde a un registro. Si el bit es 1, se recuperará el valor del registro correspondiente.  
  
 `regCount`  
 de Número de valores de registro que se van a recuperar.  
  
 `regBuffer`  
 enuncia Matriz de objetos `CORDB_REGISTER`, cada uno de los cuales recibe el valor de un registro.  
  
## <a name="remarks"></a>Notas  
 El método `GetRegisters` devuelve una matriz de valores de los registros especificados por la máscara. La matriz no contiene valores de registros cuyo bit de máscara no se ha establecido. Por lo tanto, el tamaño de la matriz de `regBuffer` debe ser igual al número de 1 de la máscara. Si el valor de `regCount` es demasiado pequeño para el número de registros indicados por la máscara, los valores de los registros numerados más altos se truncarán del conjunto. Si `regCount` es demasiado grande, los elementos `regBuffer` no utilizados no se modificarán.  
  
 Si la máscara indica un registro no disponible, se devolverá un valor indeterminado para ese registro.  
  
 El método `ICorDebugRegisterSet2::GetRegisters` es necesario para las plataformas que tienen más de 64 registros. Por ejemplo, IA64 tiene 128 registros de uso general y registros de punto flotante de 128, por lo que necesita más de 64 bits en la máscara de bits.  
  
 Si no tiene más de 64 registros, como sucede en plataformas como x86, el método `GetRegisters` realmente simplemente traduce los bytes de la matriz de bytes `mask` en un `ULONG64` y, a continuación, llama al método [ICorDebugRegisterSet:: getregisters (](icordebugregisterset-getregisters-method.md) , que toma la máscara de `ULONG64`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet2 (interfaz)](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)

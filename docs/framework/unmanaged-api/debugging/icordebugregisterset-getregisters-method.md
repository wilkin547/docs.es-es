---
title: ICorDebugRegisterSet::GetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178547"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters (Método)
Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mask`  
 [en] Una máscara de bits que especifica qué valores de registro se van a recuperar. Cada bit corresponde a un registro. Si un bit se establece en uno, se recupera el valor del registro; de lo contrario, el valor del registro no se recupera.  
  
 `regCount`  
 [en] El número de valores de registro que se van a recuperar.  
  
 `regBuffer`  
 [fuera] Matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe un valor de un registro.  
  
## <a name="remarks"></a>Observaciones  
 El tamaño de la matriz debe ser igual al número de bits establecido en uno en la máscara de bits. El `regCount` parámetro especifica el número de elementos en el búfer que recibirá los valores de registro. Si `regCount` el valor es demasiado pequeño para el número de registros indicado por la máscara, los registros numerados más altos se truncarán del conjunto. Si `regCount` el valor es demasiado `regBuffer` grande, los elementos no utilizados no se modificarán.  
  
 Si la máscara de bits especifica un `GetRegisters` registro que no está disponible, devuelve un valor indeterminado para ese registro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugRegisterSet (Interfaz)](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)

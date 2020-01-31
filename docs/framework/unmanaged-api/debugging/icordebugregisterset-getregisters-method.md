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
ms.openlocfilehash: 737993ac80b26d490915af3e97fd6a9552246aee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792120"
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
  
## <a name="parameters"></a>Parameters  
 `mask`  
 de Máscara de bits que especifica los valores de registro que se van a recuperar. Cada bit corresponde a un registro. Si un bit se establece en uno, se recupera el valor del registro; de lo contrario, no se recupera el valor del registro.  
  
 `regCount`  
 de Número de valores de registro que se van a recuperar.  
  
 `regBuffer`  
 enuncia Matriz de objetos `CORDB_REGISTER`, cada uno de los cuales recibe un valor de un registro.  
  
## <a name="remarks"></a>Notas  
 El tamaño de la matriz debe ser igual al número de bits establecido en uno en la máscara de bits. El parámetro `regCount` especifica el número de elementos en el búfer que recibirán los valores de registro. Si el valor de `regCount` es demasiado pequeño para el número de registros indicados por la máscara, los registros con mayor número se truncarán del conjunto. Si el valor `regCount` es demasiado grande, los elementos `regBuffer` no utilizados no se modificarán.  
  
 Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (interfaz)](icordebugregisterset2-interface.md)

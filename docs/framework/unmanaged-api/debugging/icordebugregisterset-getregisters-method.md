---
description: 'Más información acerca de: ICorDebugRegisterSet:: Getregisters ((método)'
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
ms.openlocfilehash: efb0f19fe9eb823912203b82267803739fc3e2cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690852"
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
 de Máscara de bits que especifica los valores de registro que se van a recuperar. Cada bit corresponde a un registro. Si un bit se establece en uno, se recupera el valor del registro; de lo contrario, no se recupera el valor del registro.  
  
 `regCount`  
 de Número de valores de registro que se van a recuperar.  
  
 `regBuffer`  
 enuncia Matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe un valor de un registro.  
  
## <a name="remarks"></a>Observaciones  

 El tamaño de la matriz debe ser igual al número de bits establecido en uno en la máscara de bits. El `regCount` parámetro especifica el número de elementos en el búfer que recibirán los valores de registro. Si el `regCount` valor es demasiado pequeño para el número de registros indicados por la máscara, los registros con mayor número se truncarán del conjunto. Si el `regCount` valor es demasiado grande, los elementos no utilizados no se `regBuffer` modificarán.  
  
 Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet (Interfaz)](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)

---
title: ICorDebugRegisterSet2::GetRegistersAvailable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 00c9939b25f395010f6ea5832b405c3e9928a223
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792025"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable (Método)
Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `numChunks`  
 [in] Tamaño de la matriz `availableRegChunks`.  
  
 `availableRegChunks`  
 enuncia Matriz de bytes, cada bit de la que corresponde a un registro. Si hay un registro disponible, se establece el bit correspondiente del registro.  
  
## <a name="remarks"></a>Notas  
 Los valores de la enumeración CorDebugRegister (especifican los registros de distintos microprocesadores. Los cinco bits superiores de cada valor son el índice de la matriz `availableRegChunks` de bytes. Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indexado. Dado un valor `CorDebugRegister` que especifica un registro determinado, la posición del registro en la máscara se determina de la manera siguiente:  
  
1. Extraiga el índice necesario para tener acceso al byte correcto en la matriz de `availableRegChunks`:  
  
     valor `CorDebugRegister` > > 3  
  
2. Extrae la posición de bit en el byte indizado, donde el bit cero es el bit menos significativo:  
  
     `CorDebugRegister` valor & 7  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet2 (interfaz)](icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)

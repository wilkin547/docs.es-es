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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b417685361126951470571e2440cc842ab1c94fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153912"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters (Método)
Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mask`  
 [in] Una máscara de bits que especifica qué registro son los valores van a recuperar. Cada bit corresponde a un registro. Si un bit se establece en uno, se recupera el valor del registro; en caso contrario, no se recupera el valor del registro.  
  
 `regCount`  
 [in] El número de valores de registro va a recuperar.  
  
 `regBuffer`  
 [out] Una matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe un valor de un registro.  
  
## <a name="remarks"></a>Comentarios  
 El tamaño de la matriz debe ser igual al número de bits establecidos en 1 en la máscara de bits. El `regCount` parámetro especifica el número de elementos en el búfer que recibirá los valores del registro. Si el `regCount` valor es demasiado pequeño para el número de registros indicado por la máscara, se truncarán los registros numerados más altos del conjunto. Si el `regCount` valor es demasiado grande, el sin usar `regBuffer` se modificarán los elementos.  
  
 Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRegisterSet (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)

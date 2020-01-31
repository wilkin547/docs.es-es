---
title: ICorDebugILCode2::GetLocalVarSigToken (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3759cfa330ac37d2ed62a0b8bb70b5e10cd9d12e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782446"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>ICorDebugILCode2::GetLocalVarSigToken (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pmdSig`  
 [out] Puntero al token `mdSignature` de la firma de variable local para esta función, o `mdSignatureNil` si no hay ninguna firma (es decir, si la función no tiene variables locales).  
  
## <a name="remarks"></a>Notas  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILCode2 (interfaz)](icordebugilcode2-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)

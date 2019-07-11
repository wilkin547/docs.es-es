---
title: ICorDebugSymbolProvider2::GetFrameProps (método)
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 274da030bbbb7c614709b5150f08f37ddf5aaf5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771165"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a>ICorDebugSymbolProvider2::GetFrameProps (método)
Devuelve la dirección virtual relativa de inicio de método de un método y el marco primario a partir de una dirección virtual relativa de código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `codeRva`  
 [in] Dirección virtual relativa de código.  
  
 `pCodeStartRva`  
 [out] Puntero a la dirección virtual relativa de inicio del método.  
  
 `pParentFrameStartRva`  
 [out] Puntero a la dirección virtual relativa de inicio del marco.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugSymbolProvider2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

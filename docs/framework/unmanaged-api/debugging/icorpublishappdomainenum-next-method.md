---
title: ICorPublishAppDomainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e4bd55a52cdbb3c242b8c3e5ff21f970b93ac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765029"
---
# <a name="icorpublishappdomainenumnext-method"></a>ICorPublishAppDomainEnum::Next (Método)
Obtiene el número especificado de dominios de aplicación que existen actualmente en el proceso, empezando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 [in] El número de elementos que se va a recuperar.  
  
 `objects`  
 [out] Recupera un puntero a la matriz de [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objetos, cada uno de los cuales representa un dominio de aplicación.  
  
 `pceltFetched`  
 [out] Puntero al número de dominios de aplicación realmente devueltos. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorPub.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublishAppDomainEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)

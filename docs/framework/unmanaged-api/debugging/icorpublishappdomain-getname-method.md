---
title: ICorPublishAppDomain::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 2f91891164f1f80617cab10347eb4a7a08762c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140356"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName (Método)
Obtiene el nombre del dominio de aplicación representado por este [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] Tamaño de la matriz `szName`.  
  
 `pcchName`  
 enuncia Puntero al número de caracteres anchos, incluido el carácter nulo, devuelto en la matriz `szName`.  
  
 `szName`  
 enuncia Matriz en la que se va a almacenar el nombre.  
  
## <a name="remarks"></a>Comentarios  
 Si `szName` no es null, el método `GetName` copia hasta `cchName` caracteres (incluido el terminador null) en `szName`. Si se devuelve un valor distinto de NULL en `pcchName`, el número real de caracteres del nombre (incluido el terminador nulo) se almacena en la matriz de `szName`.  
  
 El método `GetName` devuelve un HRESULT S_OK independientemente del número de caracteres que se hayan copiado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublishAppDomain (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)

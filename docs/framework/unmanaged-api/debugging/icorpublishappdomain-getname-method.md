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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178417"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName (Método)
Obtiene el nombre del dominio de aplicación representado por este [ICorPublishAppDomain](icorpublishappdomain-interface.md).  
  
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
 [fuera] Puntero al número de caracteres anchos, incluido `szName` el carácter nulo, devuelto en la matriz.  
  
 `szName`  
 [fuera] Matriz en la que almacenar el nombre.  
  
## <a name="remarks"></a>Observaciones  
 Si `szName` no es null, el `GetName` `cchName` método copia hasta caracteres `szName`(incluido el terminador nulo) en . Si se devuelve un `pcchName`valor distinto de null en , el número real de `szName` caracteres del nombre (incluido el terminador nulo) se almacena en la matriz.  
  
 El `GetName` método devuelve un S_OK HRESULT independientemente de cuántos caracteres se copiaron.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorPublishAppDomain (Interfaz)](icorpublishappdomain-interface.md)

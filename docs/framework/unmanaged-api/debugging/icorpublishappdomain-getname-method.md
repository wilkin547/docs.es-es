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
ms.openlocfilehash: d6b05333b9e02c4202c0fd9bdee9b5c055aa4da3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694365"
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
 enuncia Puntero al número de caracteres anchos, incluido el carácter nulo, devuelto en la `szName` matriz.  
  
 `szName`  
 enuncia Matriz en la que se va a almacenar el nombre.  
  
## <a name="remarks"></a>Comentarios  

 Si `szName` no es null, el `GetName` método copia hasta `cchName` caracteres (incluido el terminador null) en `szName` . Si se devuelve un valor distinto de NULL en `pcchName` , el número real de caracteres del nombre (incluido el terminador nulo) se almacena en la `szName` matriz.  
  
 El `GetName` método devuelve un S_OK HRESULT independientemente del número de caracteres que se hayan copiado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorPublishAppDomain (Interfaz)](icorpublishappdomain-interface.md)

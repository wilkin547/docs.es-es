---
title: ICorPublishAppDomain::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: 36c5c674f3cdf867107b9ee85a5befadc9246d78
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396305"
---
# <a name="icorpublishappdomaingetid-method"></a>ICorPublishAppDomain::GetID (Método)
Obtiene el identificador único para este [ICorPublishAppDomain](icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `puId`  
 enuncia Puntero al identificador del dominio de aplicación.  
  
## <a name="remarks"></a>Comentarios  
 El identificador es único solo en el ámbito del proceso contenedor.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublishAppDomain (Interfaz)](icorpublishappdomain-interface.md)

---
title: ICorDebugILFrame2::EnumerateTypeParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 9020fed83b1c57cae3cc492872a279afb0195983
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205170"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>ICorDebugILFrame2::EnumerateTypeParameters (Método)
Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppTyParEnum`  
 Puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.  
  
 La lista de parámetros de tipo incluye los parámetros de tipo de clase (si existen) seguidos de los parámetros de tipo de método (si existen).  
  
## <a name="remarks"></a>Observaciones  
 Use el método [IMetaDataImport2:: enumgenericparams (](../metadata/imetadataimport2-enumgenericparams-method.md) para determinar cuántos parámetros de tipo de clase y parámetros de tipo de método contiene esta lista.  
  
 Los parámetros de tipo no están siempre disponibles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
description: 'Más información sobre: ICorDebugAppDomain2:: Getarrayorpointertype ((método)'
title: ICorDebugAppDomain2::GetArrayOrPointerType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: e42d105e807bdb8c81f2d6f8ef6c2f65a4081d98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754230"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType (Método)

Obtiene una matriz del tipo especificado, o un puntero o una referencia al tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `elementType`  
 de Un valor de la enumeración CorElementType que especifica el tipo nativo subyacente (una matriz, puntero o referencia) que se va a crear.  
  
 `nRank`  
 de El rango (es decir, el número de dimensiones) de la matriz. Este valor debe ser 0 si `elementType` especifica un puntero o un tipo de referencia.  
  
 `pTypeArg`  
 de Un puntero a un objeto ICorDebugType que representa el tipo de matriz, puntero o referencia que se va a crear.  
  
 `ppType`  
 enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa la matriz construida, el tipo de puntero o el tipo de referencia.  
  
## <a name="remarks"></a>Observaciones  

 El valor de *elementType* debe ser uno de los siguientes:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY  
  
 Si el valor de *elementType* es ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nRank* debe ser cero.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

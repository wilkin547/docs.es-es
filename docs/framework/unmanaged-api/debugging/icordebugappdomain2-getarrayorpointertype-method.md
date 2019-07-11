---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd8f71ca75a795ab86c61140eacbbcfb0a18b590
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737803"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType (Método)
Obtiene una matriz de tipo especificado, o un puntero o referencia al tipo especificado.  
  
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
 [in] Un valor de la enumeración CorElementType que especifica el tipo nativo subyacente (una matriz, puntero o referencia), que se va a crear.  
  
 `nRank`  
 [in] El rango (es decir, el número de dimensiones) de la matriz. Este valor debe ser 0 si `elementType` especifica un tipo de puntero o referencia.  
  
 `pTypeArg`  
 [in] Un puntero a un objeto ICorDebugType que representa el tipo de matriz, puntero o referencia al crearse.  
  
 `ppType`  
 [out] Un puntero a la dirección de un `ICorDebugType` tipo de objeto que representa la matriz construida, tipo de puntero o referencia.  
  
## <a name="remarks"></a>Comentarios  
 El valor de *elementType* debe ser uno de los siguientes:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY  
  
 Si el valor de *elementType* es ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nRank* debe ser cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

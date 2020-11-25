---
title: ISymUnmanagedReader::GetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: f0a688aef9fbc6f7bfac85e06cbe7e76704d3230
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720536"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a>ISymUnmanagedReader::GetUserEntryPoint (Método)

Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe. Por ejemplo, este método podría ser el método Main del usuario en lugar de códigos auxiliares generados por el compilador antes del método Main.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pToken`  
 enuncia Puntero a una variable que recibe el punto de entrada.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

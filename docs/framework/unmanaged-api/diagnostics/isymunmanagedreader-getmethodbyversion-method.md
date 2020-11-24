---
title: ISymUnmanagedReader::GetMethodByVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689620"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a>ISymUnmanagedReader::GetMethodByVersion (Método)

Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia. Los números de versión se inician en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de edición y copia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  

 `token`  
 de Token del método.  
  
 `version`  
 de Versión del método.  
  
 `pRetVal`  
 enuncia Puntero a la interfaz devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

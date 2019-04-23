---
title: ISymUnmanagedWriter::RemapToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160685"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>ISymUnmanagedWriter::RemapToken (Método)
Notifica al escritor de símbolos que se ha reasignado un token de metadatos que se emitieron los metadatos. Si el escritor de símbolos ha almacenado el antiguo token en el almacén de símbolos, deberá actualizar que el token almacenado con el nuevo valor, o bien guardar la asignación del lector de símbolos correspondiente para volver a asignar durante la fase de lectura.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Parámetros  
 `oldToken`  
 [in] El token de metadatos que se ha reasignado.  
  
 `newToken`  
 [in] El nuevo token de metadatos a la que `oldToken` se volvió a asignar.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

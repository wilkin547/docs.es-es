---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efa34d262157faed2e05cd6e7517c259cd279146
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428581"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)
Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y continuar. Números de versión empiezan en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de editar y continuar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `token`  
 [in] El token de metadatos del método.  
  
 `version`  
 [in] La versión del método.  
  
 `pRetVal`  
 [out] Un puntero para el valor devuelto [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaz.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl. CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)

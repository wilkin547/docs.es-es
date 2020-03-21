---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176635"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a>ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)
Obtiene los documentos en los que este método tiene líneas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cDocs`  
 [en] La longitud del búfer `pcDocs`a la que apunta .  
  
 `pcDocs`  
 [fuera] Puntero a `ULONG32` un que recibe el tamaño, en caracteres, del búfer necesario para contener los documentos.  
  
 `documents`  
 [en] El búfer que contiene los documentos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; de lo contrario, un código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Consulte también

- [ISymENCUnmanagedMethod (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

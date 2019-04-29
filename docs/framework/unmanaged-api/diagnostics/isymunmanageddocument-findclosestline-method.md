---
title: ISymUnmanagedDocument::FindClosestLine (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab7df9b77b1820f291c1b1873b4dfb39e326bc34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939937"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a>ISymUnmanagedDocument::FindClosestLine (Método)
Devuelve la línea más próxima que sea un punto de secuencia, se especifica una línea en este documento que puede o no ser un punto de secuencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `line`  
 [in] Una línea en este documento.  
  
 `pRetVal`  
 [out] Un puntero a una variable que recibe la línea.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, un código de error.  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedDocument (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

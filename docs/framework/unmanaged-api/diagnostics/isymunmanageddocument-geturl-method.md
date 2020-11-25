---
title: ISymUnmanagedDocument::GetURL (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726943"
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL (Método)

Devuelve el localizador uniforme de recursos (URL) para este documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchUrl`  
 [in] Tamaño, en caracteres, del búfer de `szURL`.  
  
 `pcchUrl`  
 enuncia Puntero a una variable que recibe el tamaño de la dirección URL, incluida la terminación null.  
  
 `szUrl`  
 enuncia Búfer que contiene la dirección URL.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedDocument (Interfaz)](isymunmanageddocument-interface.md)

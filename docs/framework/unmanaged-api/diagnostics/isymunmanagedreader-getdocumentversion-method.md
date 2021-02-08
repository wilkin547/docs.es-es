---
description: 'Más información acerca de: ISymUnmanagedReader:: Getdocumentversion ((método)'
title: ISymUnmanagedReader::GetDocumentVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: e6877a10f0c285186330b320c9b614939f4d9e3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800206"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion (Método)

Obtiene la versión especificada del documento especificado. La versión del documento comienza en 1 y se incrementa cada vez que se actualiza el documento mediante el método [UpdateSymbolStore (](isymunmanagedreader-updatesymbolstore-method.md) . Si el `pbCurrent` parámetro es `true` , esta es la versión más reciente del documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pDoc`  
 de Documento especificado.  
  
 `version`  
 enuncia Puntero a una variable que recibe la versión del documento especificado.  
  
 `pbCurrent`  
 enuncia Un puntero a una variable que recibe `true` si se trata de la versión más reciente del documento, o `false` si no es la versión más reciente.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

---
title: ISymUnmanagedReader::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a5eb91d02ce55601f86dcadc744ef23ca430d9c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471698"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize (Método)
Inicializa el lector de símbolos con la interfaz de importador de metadatos que se asociará con, junto con el nombre de archivo del módulo de este lector.  
  
> [!NOTE]
>  Este método puede llamar a una sola vez y debe llamarse antes que cualquier otro método de lector.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Parámetros  
 `importer`  
 [in] La interfaz de importador de metadatos con el que se asociará este lector.  
  
 `filename`  
 [in] El nombre de archivo del módulo. Puede usar el `pIStream` parámetro en su lugar.  
  
 `searchPath`  
 [in] La ruta de acceso de búsqueda. Este parámetro es opcional.  
  
 `pIStream`  
 [in] La secuencia de archivos, usar como alternativa al parámetro filename.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  
 Debe especificar solo uno de los `filename` o `pIStream` parámetros, no ambos. El parámetro `searchPath` es opcional.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

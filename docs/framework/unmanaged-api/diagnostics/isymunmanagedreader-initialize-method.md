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
ms.openlocfilehash: d141d23f02b2abc92e3d4455aebe1a4057b6bb85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize (Método)
Inicializa el lector de símbolos con la interfaz de importador de metadatos que este lector estarán asociado a, junto con el nombre de archivo del módulo.  
  
> [!NOTE]
>  Este método puede llamar una sola vez y debe llamarse antes que cualquier otro método de lector.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `importer`  
 [in] La interfaz de importador de metadatos con el que se asociará este lector.  
  
 `filename`  
 [in] El nombre de archivo del módulo. Puede usar el `pIStream` parámetro en su lugar.  
  
 `searchPath`  
 [in] La ruta de acceso para buscar. Este parámetro es opcional.  
  
 `pIStream`  
 [in] Secuencia de archivo, que se utiliza como alternativa al parámetro filename.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  
 Debe especificar sólo uno de los `filename` o `pIStream` parámetros, no ambos. El parámetro `searchPath` es opcional.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

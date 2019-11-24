---
title: ISymUnmanagedWriter::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427976"
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize (Método)
Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.  
  
 This method can be called only once, and it must be called before any other writer methods. Some writers may require a file name. However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Parámetros  
 `emitter`  
 [in] A pointer to the metadata emitter interface.  
  
 `filename`  
 [in] The file name to which the debugging symbols are written. Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.  
  
 `pIStream`  
 [in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter. El parámetro `pIStream` es opcional.  
  
 `fFullBuild`  
 [in] `true` if this is a full rebuild; `false` if this is an incremental compilation.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK if the method succeeds; otherwise, E_FAIL or some other error code.  
  
## <a name="requirements"></a>Requisitos  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)

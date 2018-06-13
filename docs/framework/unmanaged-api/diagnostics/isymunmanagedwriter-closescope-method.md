---
title: ISymUnmanagedWriter::CloseScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a11f689f1fa93e1122ffcc78187c4287db7ea534
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427029"
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope (Método)
Cierra el ámbito léxico actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `endOffset`  
 [in] El desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  
 Una vez se ha cerrado un ámbito, no hay más variables se pueden definir dentro de él.  
  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) a posteriormente, define un ámbito de desplazamiento inicial y final. En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`. Los identificadores de ámbito sólo son válidos en el método actual.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

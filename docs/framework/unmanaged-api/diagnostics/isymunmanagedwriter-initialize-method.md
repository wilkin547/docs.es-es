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
ms.openlocfilehash: c702aa32e8c8d6d5c137f7968d1578715102180f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726866"
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize (Método)

Establece la interfaz emisora de metadatos a la que se asociará este escritor y establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración.  
  
 Este método solo se puede llamar una vez y se debe llamar a este método antes que a cualquier otro método de escritura. Algunos escritores pueden requerir un nombre de archivo. Sin embargo, siempre puede pasar un nombre de archivo a este método sin ningún efecto negativo en escritores que no usen el nombre de archivo.  
  
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
 de Puntero a la interfaz de emisor de metadatos.  
  
 `filename`  
 de Nombre del archivo en el que se escriben los símbolos de depuración. Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.  
  
 `pIStream`  
 de Si se especifica, el escritor de símbolos emitirá los símbolos en el especificado, en <xref:System.Runtime.InteropServices.ComTypes.IStream> lugar de en el archivo especificado en el `filename` parámetro. El `pIStream` es opcional.  
  
 `fFullBuild`  
 [in] `true` es si se trata de una recompilación completa; `false` es si se trata de una compilación incremental.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [Método Initialize2](isymunmanagedwriter-initialize2-method.md)

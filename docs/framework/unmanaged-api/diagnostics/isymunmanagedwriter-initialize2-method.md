---
title: ISymUnmanagedWriter::Initialize2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e645f79018d4ad41451faa07eba860e68b917539
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187023"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2 (Método)
Establece la interfaz emisora de metadatos con el que se asociará este sistema de escritura y el nombre de archivo de salida a la que se escribirán los símbolos de depuración. Este método también permite establecer la ubicación final del archivo de programa (PDB) de la base de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parámetros  
 `emitter`  
 [in] Un puntero a la interfaz emisora de metadatos.  
  
 `tempfilename`  
 [in] Un puntero a un `WCHAR` que contiene el nombre de archivo al que se escriben los símbolos de depuración. Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.  
  
 `pIStream`  
 [in] Si se especifica, el escritor de símbolos emite los símbolos en el determinado <xref:System.Runtime.InteropServices.ComTypes.IStream> en lugar de en el archivo especificado en el `filename` parámetro. El parámetro `pIStream` es opcional.  
  
 `fFullBuild`  
 [in] `true` si se trata de una recompilación completa; `false` si se trata de una compilación incremental.  
  
 `finalfilename`  
 [in] Un puntero a un `WCHAR` que es la cadena de ruta de acceso a la ubicación final del archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Método Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)

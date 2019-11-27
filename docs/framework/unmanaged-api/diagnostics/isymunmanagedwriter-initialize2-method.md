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
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427948"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2 (Método)
Establece la interfaz emisora de metadatos a la que se asociará este escritor y establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración. Este método también le permite establecer la ubicación final del archivo de base de datos de programa (PDB).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parámetros  
 `emitter`  
 de Puntero a la interfaz de emisor de metadatos.  
  
 `tempfilename`  
 de Puntero a una `WCHAR` que contiene el nombre de archivo en el que se escriben los símbolos de depuración. Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.  
  
 `pIStream`  
 de Si se especifica, el escritor de símbolos emite los símbolos en el <xref:System.Runtime.InteropServices.ComTypes.IStream> determinado, en lugar de en el archivo especificado en el parámetro `filename`. El parámetro `pIStream` es opcional.  
  
 `fFullBuild`  
 [in] `true` si se trata de una recompilación completa; `false` si se trata de una compilación incremental.  
  
 `finalfilename`  
 de Un puntero a un `WCHAR` que es la cadena de ruta de acceso a la ubicación final del archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)

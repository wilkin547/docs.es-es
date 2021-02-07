---
description: 'Más información acerca de: ISymUnmanagedWriter:: Initialize2 ((método)'
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
ms.openlocfilehash: 0d4c769c9f1b571296cbfe159057df083a6d5ca6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762284"
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
 de Un puntero a un `WCHAR` que contiene el nombre de archivo en el que se escriben los símbolos de depuración. Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.  
  
 `pIStream`  
 de Si se especifica, el escritor de símbolos emite los símbolos en el especificado, en <xref:System.Runtime.InteropServices.ComTypes.IStream> lugar de en el archivo especificado en el `filename` parámetro. El `pIStream` es opcional.  
  
 `fFullBuild`  
 [in] `true` es si se trata de una recompilación completa; `false` es si se trata de una compilación incremental.  
  
 `finalfilename`  
 de Un puntero a un `WCHAR` que es la cadena de ruta de acceso a la ubicación final del archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [Método Initialize](isymunmanagedwriter-initialize-method.md)

---
title: ISymUnmanagedWriter::DefineSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f07685351425a4685ac4a0c8e1b8e3c198b14187
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777303"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints (Método)
Define un grupo de puntos de secuencia dentro del método actual. Cada línea de inicio y la columna inicial define el principio de una instrucción dentro de un método. Cada línea final y columna final definen el final de una instrucción dentro de un método. Las matrices se deben ordenar en orden creciente de los desplazamientos. El desplazamiento siempre se mide desde el principio del método, en bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `document`  
 [in] El objeto de documento para el que se definen los puntos de secuencia.  
  
 `spCount`  
 [in] Un `ULONG32` que indica el tamaño de cada uno de los `offsets`, `lines`, `columns`, `endLines`, y `endColumns` búferes.  
  
 `offsets`  
 [in] El desplazamiento de los puntos de secuencia medido desde el principio del método.  
  
 `lines`  
 [in] Los números de línea inicial de los puntos de secuencia.  
  
 `columns`  
 [in] Los números de columna a partir de los puntos de secuencia.  
  
 `endLines`  
 [in] Los números de línea final de los puntos de secuencia. Este parámetro es opcional.  
  
 `endColumns`  
 [in] Los números de columna final de los puntos de secuencia. Este parámetro es opcional.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

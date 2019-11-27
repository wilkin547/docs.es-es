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
ms.openlocfilehash: 63ba108bc234e566450bb019afc63acb4e75ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427983"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints (Método)
Define un grupo de puntos de secuencia dentro del método actual. Cada línea inicial y columna inicial definen el inicio de una instrucción dentro de un método. Cada línea final y columna final definen el final de una instrucción dentro de un método. Las matrices se deben ordenar en orden ascendente de desplazamientos. El desplazamiento siempre se mide desde el inicio del método, en bytes.  
  
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
 de Objeto de documento para el que se definen los puntos de secuencia.  
  
 `spCount`  
 de `ULONG32` que indica el tamaño de cada uno de los búferes `offsets`, `lines`, `columns`, `endLines`y `endColumns`.  
  
 `offsets`  
 de Desplazamiento de los puntos de secuencia medido desde el principio del método.  
  
 `lines`  
 de Números de línea inicial de los puntos de secuencia.  
  
 `columns`  
 de Números de columna inicial de los puntos de secuencia.  
  
 `endLines`  
 de Números de línea final de los puntos de secuencia. Este parámetro es opcional.  
  
 `endColumns`  
 de Números de columna final de los puntos de secuencia. Este parámetro es opcional.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

---
title: "ISymUnmanagedWriter::DefineSequencePoints (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineSequencePoints
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints (Método)
Define un grupo de puntos de secuencia dentro del método actual. Cada línea inicial y la columna de inicio definen el comienzo de una instrucción dentro de un método. Cada línea final y cada columna final definen el final de una instrucción dentro de un método. Las matrices se deben ordenar en orden creciente de desplazamientos. El desplazamiento siempre se mide desde el principio del método, en bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `document`  
 [in] El objeto de documento para el que se definen los puntos de secuencia.  
  
 `spCount`  
 [in] A `ULONG32` que indica el tamaño de cada uno de los `offsets`, `lines`, `columns`, `endLines`, y `endColumns` búferes.  
  
 `offsets`  
 [in] El desplazamiento de los puntos de secuencia medido desde el principio del método.  
  
 `lines`  
 [in] Los números de línea inicial de los puntos de secuencia.  
  
 `columns`  
 [in] Los números de columna inicial de los puntos de secuencia.  
  
 `endLines`  
 [in] Los números de línea final de los puntos de secuencia. Este parámetro es opcional.  
  
 `endColumns`  
 [in] Los números de columna final de los puntos de secuencia. Este parámetro es opcional.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

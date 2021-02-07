---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineSequencePoints'
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
ms.openlocfilehash: 0c5ac9854ef341512f58cb1cd63ed7dfcde9962e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762336"
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
 de `ULONG32` Que indica el tamaño de cada uno de los `offsets` `lines` búferes,, `columns` , `endLines` y `endColumns` .  
  
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

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)

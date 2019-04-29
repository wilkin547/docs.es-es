---
title: ISymUnmanagedMethod::GetSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6b1e253fb7bf1a97f44e1eb05676fc356af9837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939547"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints (Método)
Obtiene todos los puntos de secuencia dentro de este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cPoints`  
 [in] Un `ULONG32` que recibe el tamaño de la `offsets`, `documents`, `lines`, `columns`, `endLines`, y `endColumns` matrices.  
  
 `pcPoints`  
 [out] Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.  
  
 `offsets`  
 [in] Una matriz de desplazamientos en los que se va a almacenar el intermedio de Microsoft desde el principio del método para los puntos de secuencia del lenguaje (MSIL).  
  
 `documents`  
 [in] Matriz en la que se va a almacenar los documentos en el que se ubican los puntos de secuencia.  
  
 `lines`  
 [in] Matriz en la que se almacenan las líneas de los documentos en el que se ubican los puntos de secuencia.  
  
 `columns`  
 [in] Matriz en la que se va a almacenar las columnas en los documentos en el que se ubican los puntos de secuencia.  
  
 `endLines`  
 [in] Matriz de líneas de los documentos en las que la secuencia de puntos finales.  
  
 `endColumns`  
 [in] Matriz de columnas de los documentos en las que la secuencia de puntos finales.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

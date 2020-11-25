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
ms.openlocfilehash: 38763e687c66dcb038a874c9c17cb0d67e547816
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699357"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints (Método)

Obtiene todos los puntos de secuencia de este método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de `ULONG32` Que recibe el tamaño de las `offsets` matrices, `documents` , `lines` , `columns` , `endLines` y `endColumns` .  
  
 `pcPoints`  
 enuncia Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.  
  
 `offsets`  
 de Matriz en la que se almacenan los desplazamientos del lenguaje intermedio de Microsoft (MSIL) desde el principio del método para los puntos de secuencia.  
  
 `documents`  
 de Matriz en la que se almacenan los documentos en los que se ubican los puntos de secuencia.  
  
 `lines`  
 de Matriz en la que se almacenan las líneas de los documentos en las que se encuentran los puntos de secuencia.  
  
 `columns`  
 de Matriz en la que se almacenan las columnas de los documentos en las que se encuentran los puntos de secuencia.  
  
 `endLines`  
 de Matriz de líneas de los documentos en las que finalizan los puntos de secuencia.  
  
 `endColumns`  
 de Matriz de columnas de los documentos en las que finalizan los puntos de secuencia.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedMethod (Interfaz)](isymunmanagedmethod-interface.md)

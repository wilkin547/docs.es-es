---
title: ISymUnmanagedMethod::GetRanges (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ca1db2bf85f42117f686a8cb483907003927c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939599"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges (Método)
Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos de lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método. La matriz es una matriz de enteros y tiene el formato [inicio, fin, inicio, final]. El número de pares del intervalo es la longitud de la matriz dividida por 2.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `document`  
 [in] El documento para el que se solicita el desplazamiento.  
  
 `line`  
 [in] La línea del documento correspondiente a los intervalos.  
  
 `column`  
 [in] Columna del documento correspondiente a los intervalos.  
  
 `cRanges`  
 [in] Tamaño de la matriz `ranges`.  
  
 `pcRanges`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los intervalos.  
  
 `ranges`  
 [out] Un puntero al búfer que recibe los intervalos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

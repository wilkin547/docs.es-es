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
ms.openlocfilehash: 8ed492b573215736c82ab6c231cc5f2e188ea013
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732156"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges (Método)

Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método. La matriz es una matriz de enteros y tiene el formato [Inicio, fin, Inicio, fin]. El número de pares de intervalo es la longitud de la matriz dividida entre 2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Documento para el que se solicita el desplazamiento.  
  
 `line`  
 de Línea del documento correspondiente a los intervalos.  
  
 `column`  
 de Columna del documento correspondiente a los intervalos.  
  
 `cRanges`  
 [in] Tamaño de la matriz `ranges`.  
  
 `pcRanges`  
 enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los intervalos.  
  
 `ranges`  
 enuncia Puntero al búfer que recibe los intervalos.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedMethod (Interfaz)](isymunmanagedmethod-interface.md)

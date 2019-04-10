---
title: ISymUnmanagedMethod::GetOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a42dc624d4de9cddebad287f6d90590f96b30272
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223659"
---
# <a name="isymunmanagedmethodgetoffset-method"></a>ISymUnmanagedMethod::GetOffset (Método)
Devuelve el desplazamiento dentro de este método que corresponde a una posición dada dentro de un documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `document`  
 [in] Un puntero al documento para el que se solicita el desplazamiento.  
  
 `line`  
 [in] La línea del documento para el que se solicita el desplazamiento.  
  
 `column`  
 [in] Columna del documento para el que se solicita el desplazamiento.  
  
 `pRetVal`  
 [out] Un puntero a un `ULONG32` que recibe los desplazamientos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedMethod (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

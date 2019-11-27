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
ms.openlocfilehash: f7993ebc15f95df97a9b45523717f318d8c435ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448937"
---
# <a name="isymunmanagedmethodgetoffset-method"></a>ISymUnmanagedMethod::GetOffset (Método)
Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `document`  
 de Un puntero al documento para el que se solicita el desplazamiento.  
  
 `line`  
 de Línea del documento para la que se solicita el desplazamiento.  
  
 `column`  
 de Columna del documento para la que se solicita el desplazamiento.  
  
 `pRetVal`  
 enuncia Puntero a un `ULONG32` que recibe los desplazamientos.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

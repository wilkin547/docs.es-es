---
title: ISymENCUnmanagedMethod::GetLineFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3106c6680750826306cffb31e599ee2260bf4ad7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136453"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset (Método)
Obtiene la información de línea asociada con un desplazamiento. Si el parámetro de desplazamiento (`dwOffset`) no es un punto de secuencia, este método obtiene la información de línea asociada con el desplazamiento anterior.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwOffset`  
 [in] Un `ULONG32` que contiene el desplazamiento.  
  
 `pline`  
 [out] Un puntero a un `ULONG32` que recibe la línea.  
  
 `pcolumn`  
 [out] Un puntero a un `ULONG32` que recibe la columna.  
  
 `pendLine`  
 [out] Un puntero a un `ULONG32` que recibe la línea final.  
  
 `pendColumn`  
 [out] Un puntero a un `ULONG32` que recibe la columna final.  
  
 `pdwStartOffset`  
 [out] Un puntero a un `ULONG32` que recibe el punto de secuencia asociado.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymENCUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

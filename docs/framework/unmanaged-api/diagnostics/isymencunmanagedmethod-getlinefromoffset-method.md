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
ms.openlocfilehash: d9a7b18e90a3038c1ffb634ccc7315143875c809
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441921"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset (Método)
Obtiene la información de línea asociada a un desplazamiento. Si el parámetro de desplazamiento ( `dwOffset` ) no es un punto de secuencia, este método obtiene la información de línea asociada al desplazamiento anterior.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Un `ULONG32` que contiene el desplazamiento.  
  
 `pline`  
 enuncia Un puntero a un `ULONG32` que recibe la línea.  
  
 `pcolumn`  
 enuncia Un puntero a un `ULONG32` que recibe la columna.  
  
 `pendLine`  
 enuncia Un puntero a un `ULONG32` que recibe la línea final.  
  
 `pendColumn`  
 enuncia Un puntero a un `ULONG32` que recibe la columna final.  
  
 `pdwStartOffset`  
 enuncia Puntero a un objeto `ULONG32` que recibe el punto de secuencia asociado.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymENCUnmanagedMethod (Interfaz)](isymencunmanagedmethod-interface.md)

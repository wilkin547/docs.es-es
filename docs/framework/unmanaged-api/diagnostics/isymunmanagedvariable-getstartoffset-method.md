---
title: ISymUnmanagedVariable::GetStartOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610371"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a>ISymUnmanagedVariable::GetStartOffset (Método)
Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario. Si se trata de una variable local dentro de un ámbito, el desplazamiento inicial se encontrará dentro de los desplazamientos definidos para el ámbito.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRetVal`  
 enuncia Un puntero a un `ULONG32` que recibe el desplazamiento de inicio.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedVariable (Interfaz)](isymunmanagedvariable-interface.md)
- [GetEndOffset (Método)](isymunmanagedvariable-getendoffset-method.md)

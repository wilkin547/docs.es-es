---
title: ISymUnmanagedNamespace::GetVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: f554fa95f552285ad92d9f780a8d77f53e6890b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707703"
---
# <a name="isymunmanagednamespacegetvariables-method"></a>ISymUnmanagedNamespace::GetVariables (Método)

Devuelve todas las variables definidas en el ámbito global dentro de este espacio de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cVars`  
 de `ULONG32` Que indica el tamaño de la `pVars` matriz.  
  
 `pcVars`  
 enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.  
  
 `pVars`  
 enuncia Un puntero a un búfer que contiene los espacios de nombres.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedNamespace (Interfaz)](isymunmanagednamespace-interface.md)

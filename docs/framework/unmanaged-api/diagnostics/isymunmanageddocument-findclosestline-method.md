---
title: ISymUnmanagedDocument::FindClosestLine (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 0e95255479792c7056bee7ee4f6c507e0f41eb6a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449218"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a>ISymUnmanagedDocument::FindClosestLine (Método)
Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `line`  
 de Una línea en este documento.  
  
 `pRetVal`  
 enuncia Puntero a una variable que recibe la línea.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedDocument (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

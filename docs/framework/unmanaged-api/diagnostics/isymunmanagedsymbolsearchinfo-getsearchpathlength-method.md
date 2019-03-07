---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 892da7ec41c75e50f7f2cb086b05e466478e1ced
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484100"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a>ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)
Obtiene la longitud de ruta de acceso de búsqueda.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pcchPath`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la longitud de ruta de acceso de búsqueda.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedSymbolSearchInfo (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

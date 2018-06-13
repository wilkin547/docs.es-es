---
title: ISymUnmanagedNamespace::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aeb3c4e9a1d87b2d93a310b88c340aec0955a845
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425303"
---
# <a name="isymunmanagednamespacegetname-method"></a>ISymUnmanagedNamespace::GetName (Método)
Obtiene el nombre de este espacio de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] A `ULONG32` que indica el tamaño de la `szName` búfer.  
  
 `pcchName`  
 [out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre de espacio de nombres, incluida la terminación null.  
  
 `szName`  
 [out] Un puntero a un búfer que contiene el nombre de espacio de nombres.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedNamespace (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)

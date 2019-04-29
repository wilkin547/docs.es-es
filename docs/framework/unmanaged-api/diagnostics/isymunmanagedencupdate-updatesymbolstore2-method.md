---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82f2f335299cfd3041dcecc7d176cb77ce54ae96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939677"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)
Permite que un compilador que omita las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumpla los requisitos. Con la antigua información de línea PDB y un carácter delta para todas las líneas en la función se puede determinar la información de línea correctos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pIStream`  
 [in] Un puntero a un [IStream](/windows/desktop/api/objidl/nn-objidl-istream) que contiene la información de línea.  
  
 `pDeltaLines`  
 [in] Un puntero a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) estructura que contiene las líneas que han cambiado.  
  
 `cDeltaLines`  
 [in] Un `ULONG` que representa el número de líneas que han cambiado.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedENCUpdate (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

---
title: ISymUnmanagedENCUpdate::UpdateMethodLines (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50d9ac08b01a67df68ff077721ff5421fbc27707
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>ISymUnmanagedENCUpdate::UpdateMethodLines (Método)
Permite actualizar la información de línea para un método que no se han recopilado, pero cuyos líneas se han movido por separado. Se permite un carácter delta para cada instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mdMethodToken`  
 [in] Los metadatos del token del método.  
  
 `pDeltas`  
 [in] Una matriz de `INT32` valores que indica los caracteres delta para cada punto de secuencia en el método.  
  
 `cDeltas`  
 [in] A `ULONG` que contiene el tamaño de la `pDeltas` parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedENCUpdate (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

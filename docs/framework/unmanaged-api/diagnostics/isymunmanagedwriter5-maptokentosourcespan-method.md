---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 0f00dd34ffbdd58a46260132d8d7ace74ec2f294
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501682"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a>ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.  
  
 Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también:

- [ISymUnmanagedWriter5 (Interfaz)](isymunmanagedwriter5-interface.md)

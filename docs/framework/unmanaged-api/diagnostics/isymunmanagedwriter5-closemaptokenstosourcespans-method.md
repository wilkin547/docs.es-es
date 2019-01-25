---
title: ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4b41854d5d9324169b1873f431ef81c0a4c5be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677924"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a>ISymUnmanagedWriter5::CloseMapTokensToSourceSpans (Método)
Cerrar la sección de datos personalizado especial para información sobre la asignación de intervalo de origen de token. Después de cerrar, no se puede agregar ninguna información de asignación.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también
- [ISymUnmanagedWriter5 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222684"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a>ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
Abra una sección especial de datos personalizados para emitir la información de asignación de intervalo de origen de token en. Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter5 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)

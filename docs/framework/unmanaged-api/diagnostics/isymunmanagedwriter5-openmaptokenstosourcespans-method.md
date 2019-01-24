---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60c1984e6193481efdaaeb82a2bc025aef67a33f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534451"
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

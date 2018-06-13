---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fd7c2bd4fae94d1ef5021b558a04b734803b68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430562"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5 (Interfaz)
ISymUnmanagedWriter5 (interfaz).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Cierre la sección especial de datos personalizado para la información de asignación de intervalo de origen de token. Una vez que se ha cerrado puede agregarse no hay más información de asignación.|  
|[MapTokenToSourceSpan (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|Mapas que abarcan el token de metadatos especificado en la línea de código fuente en el archivo de origen especificado.<br /><br /> Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).|  
|[OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de origen de token en. Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedWriter4 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)

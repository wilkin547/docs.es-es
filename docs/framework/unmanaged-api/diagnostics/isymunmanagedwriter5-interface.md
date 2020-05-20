---
title: ISymUnmanagedWriter5 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: bdc630c3c94c7d03b736efa0a95665f10aac7c6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609435"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5 (Interfaz)
Interfaz ISymUnmanagedWriter5.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Métodos  
 Esta interfaz contiene los siguientes métodos:  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Cierre la sección datos personalizados especiales para obtener información sobre la asignación de intervalos de token a origen. Una vez cerrado, no se puede agregar más información de asignación.|  
|[Método MapTokenToSourceSpan](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.<br /><br /> Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).|  
|[Método OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en. Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter4 (Interfaz)](isymunmanagedwriter4-interface.md)

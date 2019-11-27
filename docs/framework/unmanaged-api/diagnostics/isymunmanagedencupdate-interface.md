---
title: ISymUnmanagedENCUpdate (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449005"
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate (Interfaz)
Proporciona funciones para la característica editar y continuar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetLocalVariableCount (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|Obtiene el número de variables locales.|  
|[GetLocalVariables (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|Obtiene las variables locales.|  
|[InitializeForEnc (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .|  
|[UpdateMethodLines (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado. Se permite una diferencia de cada instrucción.|  
|[UpdateSymbolStore2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos. La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

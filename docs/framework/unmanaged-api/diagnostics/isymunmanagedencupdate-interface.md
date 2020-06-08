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
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501747"
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate (Interfaz)
Proporciona funciones para la característica editar y continuar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetLocalVariableCount](isymunmanagedencupdate-getlocalvariablecount-method.md)|Obtiene el número de variables locales.|  
|[Método GetLocalVariables](isymunmanagedencupdate-getlocalvariables-method.md)|Obtiene las variables locales.|  
|[Método InitializeForEnc](isymunmanagedencupdate-initializeforenc-method.md)|Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](isymunmanagedencupdate-updatesymbolstore2-method.md) .|  
|[Método UpdateMethodLines](isymunmanagedencupdate-updatemethodlines-method.md)|Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado. Se permite una diferencia de cada instrucción.|  
|[Método UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md)|Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos. La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)

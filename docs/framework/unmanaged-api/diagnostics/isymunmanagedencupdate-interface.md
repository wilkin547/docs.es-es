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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 378322c28d59b2a6e7c09f2f2c4bf55bb019d01d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939703"
---
# <a name="isymunmanagedencupdate-interface"></a>ISymUnmanagedENCUpdate (Interfaz)
Proporciona funciones para la característica Editar y continuar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetLocalVariableCount (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|Obtiene el número de variables locales.|  
|[GetLocalVariables (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|Obtiene las variables locales.|  
|[InitializeForEnc (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|Permite que los límites del método que debe calcularse antes de la primera llamada a la [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) método.|  
|[UpdateMethodLines (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han movido por separado. Se permite un carácter delta para cada instrucción.|  
|[UpdateSymbolStore2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|Permite que un compilador que omita las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumple los requisitos. Con la antigua información de línea PDB y un carácter delta para todas las líneas en la función se puede determinar la información de línea correctos.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

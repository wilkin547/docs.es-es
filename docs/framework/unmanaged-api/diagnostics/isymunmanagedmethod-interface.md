---
title: ISymUnmanagedMethod (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod
helpviewer_keywords: ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6305625c3d02dbd126a284287e19b319e21eeba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod (Interfaz)
Representa un método en el almacén de símbolos. Esta interfaz proporciona acceso a solo los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Obtiene el espacio de nombres dentro del cual se define este método.|  
|[GetOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Devuelve el desplazamiento dentro de este método que corresponde a una posición especificada dentro de un documento.|  
|[GetParameters (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Obtiene los parámetros de este método.|  
|[GetRanges (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.|  
|[GetRootScope (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Obtiene el ámbito léxico raíz dentro de este método. Este ámbito abarca el método completo.|  
|[GetScopeFromOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Obtiene el ámbito léxico más envolvente dentro de este método que contiene el desplazamiento especificado.|  
|[GetSequencePointCount (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Obtiene el número de puntos de secuencia dentro de este método.|  
|[GetSequencePoints (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Obtiene todos los puntos de secuencia dentro de este método.|  
|[GetSourceStartEnd (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Obtiene las posiciones de documento de inicio y finalización para el origen de este método.|  
|[GetToken (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Devuelve el token de metadatos para este método.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

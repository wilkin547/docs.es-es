---
title: ISymUnmanagedMethod (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615129"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod (Interfaz)
Representa un método dentro del almacén de símbolos. Esta interfaz proporciona acceso únicamente a los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetNamespace](isymunmanagedmethod-getnamespace-method.md)|Obtiene el espacio de nombres en el que se define este método.|  
|[Método GetOffset](isymunmanagedmethod-getoffset-method.md)|Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.|  
|[Método GetParameters](isymunmanagedmethod-getparameters-method.md)|Obtiene los parámetros de este método.|  
|[Método GetRanges](isymunmanagedmethod-getranges-method.md)|Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.|  
|[Método GetRootScope](isymunmanagedmethod-getrootscope-method.md)|Obtiene el ámbito léxico raíz dentro de este método. Este ámbito abarca el método completo.|  
|[Método GetScopeFromOffset](isymunmanagedmethod-getscopefromoffset-method.md)|Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.|  
|[Método GetSequencePointCount](isymunmanagedmethod-getsequencepointcount-method.md)|Obtiene el recuento de puntos de secuencia dentro de este método.|  
|[Método GetSequencePoints](isymunmanagedmethod-getsequencepoints-method.md)|Obtiene todos los puntos de secuencia de este método.|  
|[Método GetSourceStartEnd](isymunmanagedmethod-getsourcestartend-method.md)|Obtiene las posiciones de documento inicial y final para el origen de este método.|  
|[GetToken (Método)](isymunmanagedmethod-gettoken-method.md)|Devuelve el símbolo (token) de metadatos para este método.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)

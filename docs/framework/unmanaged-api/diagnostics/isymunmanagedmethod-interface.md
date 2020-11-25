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
ms.openlocfilehash: b72a77fecd15a43efbddd9dfd4618897c3372f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699279"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod (Interfaz)

Representa un método dentro del almacén de símbolos. Esta interfaz proporciona acceso únicamente a los atributos relacionados con símbolos de un método, en lugar de los atributos relacionados con el tipo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetNamespace](isymunmanagedmethod-getnamespace-method.md)|Obtiene el espacio de nombres en el que se define este método.|  
|[GetOffset (Método)](isymunmanagedmethod-getoffset-method.md)|Devuelve el desplazamiento dentro de este método que corresponde a una posición determinada dentro de un documento.|  
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
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)

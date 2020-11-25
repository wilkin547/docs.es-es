---
title: ISymUnmanagedWriter (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: fddfd2a163f6e6513b648ee0b724c0b5bd54c81a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722939"
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter (Interfaz)

Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (Método)](isymunmanagedwriter-abort-method.md)|Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.|  
|[Close (Método)](isymunmanagedwriter-close-method.md)|Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.|  
|[Método CloseMethod](isymunmanagedwriter-closemethod-method.md)|Cierra el método actual. Una vez que se cierra un método, no se pueden definir más símbolos en él.|  
|[Método CloseNamespace](isymunmanagedwriter-closenamespace-method.md)|Cierra el espacio de nombres abierto más recientemente.|  
|[Método CloseScope](isymunmanagedwriter-closescope-method.md)|Cierra el ámbito léxico actual.|  
|[Método DefineConstant](isymunmanagedwriter-defineconstant-method.md)|Define un nombre para un valor constante.|  
|[Método DefineDocument](isymunmanagedwriter-definedocument-method.md)|Define un documento de origen.|  
|[DefineField (Método)](isymunmanagedwriter-definefield-method.md)|Define una única variable que no está dentro de un método.|  
|[Método DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)|Define una única variable global.|  
|[Método DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)|Define una única variable en el ámbito léxico actual.|  
|[Método DefineParameter](isymunmanagedwriter-defineparameter-method.md)|Define un único parámetro en el método actual.|  
|[Método DefineSequencePoints](isymunmanagedwriter-definesequencepoints-method.md)|Define un grupo de puntos de secuencia dentro del método actual.|  
|[Método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md)|Devuelve la información necesaria para que un compilador escriba la entrada del directorio de depuración en el encabezado de archivo portable ejecutable (PE).|  
|[Initialize (Método)](isymunmanagedwriter-initialize-method.md)|Establece la interfaz emisora de metadatos a la que se asociará este escritor y establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración.|  
|[Método Initialize2](isymunmanagedwriter-initialize2-method.md)|Establece la interfaz emisora de metadatos a la que se asociará este sistema de escritura, establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración y establece la ubicación final del archivo de base de datos de programa (PDB).|  
|[Método OpenMethod](isymunmanagedwriter-openmethod-method.md)|Abre un método en el que se emite información de símbolos.|  
|[Método OpenNamespace](isymunmanagedwriter-opennamespace-method.md)|Abre un nuevo espacio de nombres.|  
|[OpenScope (Método)](isymunmanagedwriter-openscope-method.md)|Abre un nuevo ámbito léxico en el método actual.|  
|[Método RemapToken](isymunmanagedwriter-remaptoken-method.md)|Notifica al escritor de símbolos que se ha reasignado un token de metadatos cuando se emitieron los metadatos.|  
|[Método SetMethodSourceRange](isymunmanagedwriter-setmethodsourcerange-method.md)|Especifica el principio y final reales de un método dentro de un archivo de código fuente.|  
|[Método SetScopeRange](isymunmanagedwriter-setscoperange-method.md)|Define el intervalo de desplazamiento del ámbito léxico especificado.|  
|[Método SetSymAttribute](isymunmanagedwriter-setsymattribute-method.md)|Define un atributo personalizado basado en su nombre.|  
|[Método SetUserEntryPoint](isymunmanagedwriter-setuserentrypoint-method.md)|Especifica el método definido por el usuario que es el punto de entrada de este módulo.|  
|[Método UsingNamespace](isymunmanagedwriter-usingnamespace-method.md)|Especifica que el nombre completo del espacio de nombres especificado se está usando en el ámbito léxico abierto actualmente.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2 (Interfaz)](isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3 (Interfaz)](isymunmanagedwriter3-interface.md)

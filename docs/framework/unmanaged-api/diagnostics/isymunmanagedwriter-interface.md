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
ms.openlocfilehash: fc19ee25e903046daef376e4297c8feb3d01ad47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427940"
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter (Interfaz)
Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, ámbitos léxicos y variables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.|  
|[Close (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.|  
|[CloseMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Cierra el método actual. Una vez que se cierra un método, no se pueden definir más símbolos en él.|  
|[CloseNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Cierra el espacio de nombres abierto más recientemente.|  
|[CloseScope (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Cierra el ámbito léxico actual.|  
|[DefineConstant (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Define un nombre para un valor constante.|  
|[DefineDocument (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Define un documento de origen.|  
|[DefineField (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Define una única variable que no está dentro de un método.|  
|[DefineGlobalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Define una única variable global.|  
|[DefineLocalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Define una única variable en el ámbito léxico actual.|  
|[DefineParameter (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Define un único parámetro en el método actual.|  
|[DefineSequencePoints (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Define un grupo de puntos de secuencia dentro del método actual.|  
|[GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Devuelve la información necesaria para que un compilador escriba la entrada del directorio de depuración en el encabezado de archivo portable ejecutable (PE).|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Establece la interfaz emisora de metadatos a la que se asociará este escritor y establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración.|  
|[Initialize2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Establece la interfaz emisora de metadatos a la que se asociará este sistema de escritura, establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración y establece la ubicación final del archivo de base de datos de programa (PDB).|  
|[OpenMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Abre un método en el que se emite información de símbolos.|  
|[OpenNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Abre un nuevo espacio de nombres.|  
|[OpenScope (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Abre un nuevo ámbito léxico en el método actual.|  
|[RemapToken (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifica al escritor de símbolos que se ha reasignado un token de metadatos cuando se emitieron los metadatos.|  
|[SetMethodSourceRange (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Especifica el principio y el final de un método dentro de un archivo de código fuente.|  
|[SetScopeRange (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Define el intervalo de desplazamiento del ámbito léxico especificado.|  
|[SetSymAttribute (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Define un atributo personalizado basado en su nombre.|  
|[SetUserEntryPoint (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Especifica el método definido por el usuario que es el punto de entrada de este módulo.|  
|[UsingNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Especifica que el nombre completo del espacio de nombres especificado se está usando en el ámbito léxico abierto actualmente.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

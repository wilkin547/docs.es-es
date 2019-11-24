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
Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Closes the symbol writer without committing the symbols to the symbol store.|  
|[Close (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Closes the symbol writer after committing the symbols to the symbol store.|  
|[CloseMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Cierra el método actual. Once a method is closed, no more symbols can be defined within it.|  
|[CloseNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Closes the most recently opened namespace.|  
|[CloseScope (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Cierra el ámbito léxico actual.|  
|[DefineConstant (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Defines a name for a constant value.|  
|[DefineDocument (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Define un documento de origen.|  
|[DefineField (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Defines a single variable that is not within a method.|  
|[DefineGlobalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Defines a single global variable.|  
|[DefineLocalVariable (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Define una única variable en el ámbito léxico actual.|  
|[DefineParameter (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Defines a single parameter in the current method.|  
|[DefineSequencePoints (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Define un grupo de puntos de secuencia dentro del método actual.|  
|[GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.|  
|[Initialize2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Sets the metadata emitter interface with which this writer will be associated, sets the output file name to which the debugging symbols will be written, and sets the final location of the program database (PDB) file.|  
|[OpenMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Opens a method into which symbol information is emitted.|  
|[OpenNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Abre un nuevo espacio de nombres.|  
|[OpenScope (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Abre un nuevo ámbito léxico en el método actual.|  
|[RemapToken (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.|  
|[SetMethodSourceRange (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Specifies the true start and end of a method within a source file.|  
|[SetScopeRange (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Define el intervalo de desplazamiento del ámbito léxico especificado.|  
|[SetSymAttribute (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Defines a custom attribute based upon its name.|  
|[SetUserEntryPoint (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Specifies the user-defined method that is the entry point for this module.|  
|[UsingNamespace (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.|  
  
## <a name="requirements"></a>Requisitos  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

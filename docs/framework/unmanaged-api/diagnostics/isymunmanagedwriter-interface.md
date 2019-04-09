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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ac95cd5b79a2e1762fa9adf29d4d7926ab4ab7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150588"
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter (Interfaz)
Representa un escritor de símbolos y proporciona métodos para definir documentos, puntos de secuencia, los ámbitos léxicos y variables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (Método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.|  
|[Close (Método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.|  
|[Método CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Cierra el método actual. Una vez cerrado un método, no hay más símbolos se pueden definir dentro de él.|  
|[Método CloseNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Cierra la última abre el espacio de nombres.|  
|[Método CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Cierra el ámbito léxico actual.|  
|[Método DefineConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Define un nombre para un valor constante.|  
|[Método DefineDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Define un documento de origen.|  
|[Método DefineField](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Define una única variable que no está dentro de un método.|  
|[Método DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Define una única variable global.|  
|[Método DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Define una única variable en el ámbito léxico actual.|  
|[Método DefineParameter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Define un único parámetro del método actual.|  
|[Método DefineSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Define un grupo de puntos de secuencia dentro del método actual.|  
|[Método GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Devuelve la información necesaria para que un compilador escribir la entrada de directorio de depuración en el encabezado del archivo portable ejecutable (PE).|  
|[Método Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Establece la interfaz emisora de metadatos con el que se asociará este sistema de escritura y el nombre de archivo de salida a la que se escribirán los símbolos de depuración.|  
|[Método Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Establece la interfaz emisora de metadatos con el que se asociará este sistema de escritura, Establece el nombre de archivo de salida a la que se escribirán los símbolos de depuración y establece la ubicación final del archivo de programa (PDB) de la base de datos.|  
|[Método OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Abre un método en el símbolo que se emite la información.|  
|[Método OpenNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Abre un nuevo espacio de nombres.|  
|[Método OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Abre un nuevo ámbito léxico en el método actual.|  
|[Método RemapToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifica al escritor de símbolos que se ha reasignado un token de metadatos que se emitieron los metadatos.|  
|[Método SetMethodSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Especifica el principio y final reales de un método dentro de un archivo de origen.|  
|[Método SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Define el intervalo de desplazamiento del ámbito léxico especificado.|  
|[Método SetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Define un atributo personalizado basándose en su nombre.|  
|[Método SetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Especifica el método definido por el usuario que es el punto de entrada para este módulo.|  
|[Método UsingNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Especifica que se utiliza el nombre completo del espacio de nombres determinado dentro del ámbito léxico abierto actualmente.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2 (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3 (Interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)

---
title: ISymUnmanagedReader (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a78616ea1dccdf82c4e00d23d2ff630c98cb4e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader (Interfaz)
Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables del sistema en un almacén de símbolos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetDocument (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Busca un documento.|  
|[GetDocuments (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.|  
|[GetDocumentVersion (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Obtiene la versión especificada del documento especificado.|  
|[GetGlobalVariables (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Devuelve todas las variables globales.|  
|[GetMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Obtiene un método del lector de símbolos, dado un token de método.|  
|[GetMethodByVersion (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.|  
|[GetMethodFromDocumentPosition (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.|  
|[GetMethodsFromDocumentPosition (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Devuelve una matriz de los métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.|  
|[GetMethodVersion (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Obtiene la versión del método.|  
|[GetNamespaces (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.|  
|[GetSymAttribute (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Obtiene un atributo personalizado basándose en su nombre.|  
|[GetSymbolStoreFileName (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Proporciona el nombre de archivo en disco del almacén de símbolos.|  
|[GetUserEntryPoint (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.|  
|[GetVariables (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Devuelve una variable no local, según su elemento primario y el nombre.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Inicializa el lector de símbolos con la interfaz de importador de metadatos que este lector estarán asociado a, junto con el nombre de archivo del módulo.|  
|[ReplaceSymbolStore (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.|  
|[UpdateSymbolStore (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Actualiza el almacén de símbolos existente con un almacén de símbolos delta.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedReader2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)

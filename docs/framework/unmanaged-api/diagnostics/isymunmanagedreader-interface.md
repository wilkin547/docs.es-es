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
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615467"
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader (Interfaz)
Representa un lector de símbolos que proporciona acceso a los documentos, métodos y variables de un almacén de símbolos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetDocument](isymunmanagedreader-getdocument-method.md)|Busca un documento.|  
|[Método GetDocuments](isymunmanagedreader-getdocuments-method.md)|Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.|  
|[Método GetDocumentVersion](isymunmanagedreader-getdocumentversion-method.md)|Obtiene la versión especificada del documento especificado.|  
|[Método GetGlobalVariables](isymunmanagedreader-getglobalvariables-method.md)|Devuelve todas las variables globales.|  
|[Método GetMethod](isymunmanagedreader-getmethod-method.md)|Obtiene un método del lector de símbolos, dado un token de método.|  
|[Método GetMethodByVersion](isymunmanagedreader-getmethodbyversion-method.md)|Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia.|  
|[Método GetMethodFromDocumentPosition](isymunmanagedreader-getmethodfromdocumentposition-method.md)|Devuelve el método que contiene el punto de interrupción en la posición especificada de un documento.|  
|[Método GetMethodsFromDocumentPosition](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.|  
|[Método GetMethodVersion](isymunmanagedreader-getmethodversion-method.md)|Obtiene la versión del método.|  
|[Método GetNamespaces](isymunmanagedreader-getnamespaces-method.md)|Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.|  
|[Método GetSymAttribute](isymunmanagedreader-getsymattribute-method.md)|Obtiene un atributo personalizado basado en su nombre.|  
|[Método GetSymbolStoreFileName](isymunmanagedreader-getsymbolstorefilename-method.md)|Proporciona el nombre de archivo en disco del almacén de símbolos.|  
|[Método GetUserEntryPoint](isymunmanagedreader-getuserentrypoint-method.md)|Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe.|  
|[Método GetVariables](isymunmanagedreader-getvariables-method.md)|Devuelve una variable no local, dados su nombre y elemento primario.|  
|[Método Initialize](isymunmanagedreader-initialize-method.md)|Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.|  
|[Método ReplaceSymbolStore](isymunmanagedreader-replacesymbolstore-method.md)|Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.|  
|[Método UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)|Actualiza el almacén de símbolos existente con un almacén de símbolos delta.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader2 (Interfaz)](isymunmanagedreader2-interface.md)

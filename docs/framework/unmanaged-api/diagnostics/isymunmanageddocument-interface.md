---
title: ISymUnmanagedDocument (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615571"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument (Interfaz)
Representa un documento al que hace referencia un almacén de símbolos. Un documento se define mediante un localizador uniforme de recursos (URL) y un GUID de tipo de documento. Puede buscar el documento sin tener en consideración cómo se almacena mediante la dirección URL y el GUID del tipo de documento. Puede almacenar el origen del documento en el almacén de símbolos y recuperarlo a través de esta interfaz.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método FindClosestLine](isymunmanageddocument-findclosestline-method.md)|Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.|  
|[Método GetCheckSum](isymunmanageddocument-getchecksum-method.md)|Obtiene la suma de comprobación.|  
|[Método GetCheckSumAlgorithmId](isymunmanageddocument-getchecksumalgorithmid-method.md)|Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.|  
|[Método GetDocumentType](isymunmanageddocument-getdocumenttype-method.md)|Obtiene el tipo de documento de este documento.|  
|[Método GetLanguage](isymunmanageddocument-getlanguage-method.md)|Obtiene el identificador de idioma de este documento.|  
|[Método GetLanguageVendor](isymunmanageddocument-getlanguagevendor-method.md)|Obtiene el proveedor de lenguaje de este documento.|  
|[Método GetSourceLength](isymunmanageddocument-getsourcelength-method.md)|Obtiene la longitud, en bytes, del código fuente incrustado.|  
|[Método GetSourceRange](isymunmanageddocument-getsourcerange-method.md)|Devuelve el intervalo especificado del código fuente incrustado en el búfer especificado.|  
|[Método GetURL](isymunmanageddocument-geturl-method.md)|Devuelve la dirección URL de este documento.|  
|[Método HasEmbeddedSource](isymunmanageddocument-hasembeddedsource-method.md)|Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .|  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)

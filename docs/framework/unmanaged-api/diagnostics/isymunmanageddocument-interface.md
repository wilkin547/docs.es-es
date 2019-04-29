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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939781"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument (Interfaz)
Representa un documento al que hace referencia un almacén de símbolos. Un documento se define mediante un localizador uniforme de recursos (URL) y un GUID de tipo de documento. Puede buscar el documento, independientemente de cómo se almacenan utilizando la dirección URL y GUID del tipo de documento. Puede almacenar el código fuente del documento en el almacén de símbolos y recuperarlo a través de esta interfaz.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[FindClosestLine (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Devuelve la línea más próxima que sea un punto de secuencia, se especifica una línea en este documento que puede o no ser un punto de secuencia.|  
|[GetCheckSum (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Obtiene la suma de comprobación.|  
|[GetCheckSumAlgorithmId (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.|  
|[GetDocumentType (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Obtiene el tipo de documento de este documento.|  
|[GetLanguage (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Obtiene el identificador de idioma de este documento.|  
|[GetLanguageVendor (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Obtiene el proveedor de lenguaje de este documento.|  
|[GetSourceLength (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Obtiene la longitud, en bytes, del código fuente incrustado.|  
|[GetSourceRange (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Devuelve el intervalo especificado de código fuente incrustado en el búfer especificado.|  
|[GetURL (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Devuelve la dirección URL de este documento.|  
|[HasEmbeddedSource (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; en caso contrario, devuelve `false`.|  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

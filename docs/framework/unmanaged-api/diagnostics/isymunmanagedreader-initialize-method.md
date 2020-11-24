---
title: ISymUnmanagedReader::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: 6193d91c8cbe0efa7cd68b97b9262acf72c9ea0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675885"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize (Método)

Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.  
  
> [!NOTE]
> Este método solo se puede llamar una vez y se debe llamar a antes que a cualquier otro método de lectura.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Parámetros  

 `importer`  
 de La interfaz de importador de metadatos a la que se asociará este lector.  
  
 `filename`  
 de Nombre de archivo del módulo. En su lugar, puede usar el `pIStream` parámetro.  
  
 `searchPath`  
 de Ruta de acceso que se va a buscar. Este parámetro es opcional.  
  
 `pIStream`  
 de El flujo de archivo, que se usa como alternativa al parámetro FILENAME.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="remarks"></a>Comentarios  

 Solo tiene que especificar uno de los `filename` `pIStream` parámetros o, no ambos. El `searchPath` es opcional.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

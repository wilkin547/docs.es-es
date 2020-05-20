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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615480"
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
  
## <a name="remarks"></a>Observaciones  
 Solo tiene que especificar uno de los `filename` `pIStream` parámetros o, no ambos. El `searchPath` es opcional.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

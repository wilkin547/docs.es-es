---
description: 'Más información acerca de: ISymUnmanagedReader:: Initialize (método)'
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
ms.openlocfilehash: cf7f5df3efed7823fc36bd6c9fc56e0c49d17443
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763883"
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
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

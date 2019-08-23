---
title: ISymUnmanagedReader::UpdateSymbolStore (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939003"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore (Método)
Actualiza el almacén de símbolos existente con un almacén de símbolos delta. Este método se usa en escenarios de edición y continuación para actualizar el almacén de símbolos de modo que coincida con las diferencias con el archivo portable ejecutable (PE) original.  
  
> [!NOTE]
> Solo se debe especificar uno de los `filename` parámetros `pIStream` o, no ambos. Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo. Si `pIStream` se especifica, el almacén se actualizará con los datos <xref:System.Runtime.InteropServices.ComTypes.IStream>de.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parámetros  
 `filename`  
 de Nombre del archivo que contiene el almacén de símbolos.  
  
 `pIStream`  
 de El flujo de archivo, que se usa como alternativa `filename` al parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

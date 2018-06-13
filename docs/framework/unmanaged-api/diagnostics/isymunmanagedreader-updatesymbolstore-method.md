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
ms.openlocfilehash: 81f9db872e9904d2297221e266be710837d0fb66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427387"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore (Método)
Actualiza el almacén de símbolos existente con un almacén de símbolos delta. Este método se utiliza en escenarios de editar y continuar para actualizar el almacén de símbolos delta coincidan con el archivo ejecutable portable (PE) original.  
  
> [!NOTE]
>  Es necesario especificar sólo uno de los `filename` o `pIStream` parámetros, no ambos. Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo. Si `pIStream` se especifica, el almacén se actualizará con los datos de la <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `filename`  
 [in] El nombre del archivo que contiene el almacén de símbolos.  
  
 `pIStream`  
 [in] La secuencia de archivos que se utiliza como una alternativa a la `filename` parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

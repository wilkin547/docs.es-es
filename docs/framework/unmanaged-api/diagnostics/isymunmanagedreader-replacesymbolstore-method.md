---
title: ISymUnmanagedReader::ReplaceSymbolStore (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: db2137146ded5200e05bbf88e23ae599f3eb7dec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615454"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore (Método)
Reemplaza el almacén de símbolos existente con un almacén de símbolos delta. Este método es similar al método [UpdateSymbolStore (](isymunmanagedreader-updatesymbolstore-method.md) , salvo que el Delta dado actúa como un reemplazo completo en lugar de una actualización.  
  
> [!NOTE]
> Solo se debe especificar uno de los `filename` `pIStream` parámetros o, no ambos. Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo. Si `pIStream` se especifica, el almacén se actualizará con los datos de <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parámetros  
 `filename`  
 de Nombre del archivo que contiene el almacén de símbolos.  
  
 `pIStream`  
 de El flujo de archivo, que se usa como alternativa al `filename` parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedReader (Interfaz)](isymunmanagedreader-interface.md)

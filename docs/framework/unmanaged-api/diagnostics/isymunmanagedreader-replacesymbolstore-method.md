---
title: "ISymUnmanagedReader::ReplaceSymbolStore (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bedceac4661204bb72e59981450d7fee488857b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="9f371-102">ISymUnmanagedReader::ReplaceSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="9f371-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="9f371-103">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="9f371-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="9f371-104">Este método es similar a la [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) método, salvo que el símbolo delta indicado actúa como un reemplazo completo en lugar de una actualización.</span><span class="sxs-lookup"><span data-stu-id="9f371-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f371-105">Es necesario especificar sólo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="9f371-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="9f371-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="9f371-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="9f371-107">Si `pIStream` se especifica, el almacén se actualizará con los datos de la <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="9f371-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f371-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f371-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f371-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f371-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="9f371-110">[in] El nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9f371-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9f371-111">[in] La secuencia de archivos que se utiliza como una alternativa a la `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="9f371-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f371-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f371-112">Return Value</span></span>  
 <span data-ttu-id="9f371-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9f371-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f371-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f371-114">Requirements</span></span>  
 <span data-ttu-id="9f371-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9f371-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f371-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f371-116">See Also</span></span>  
 [<span data-ttu-id="9f371-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f371-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

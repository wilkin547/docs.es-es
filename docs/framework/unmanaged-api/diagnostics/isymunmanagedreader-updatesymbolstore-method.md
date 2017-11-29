---
title: "ISymUnmanagedReader::UpdateSymbolStore (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.UpdateSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cfea77814069f6689f7492608548836fdafa591b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="239db-102">ISymUnmanagedReader::UpdateSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="239db-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="239db-103">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="239db-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="239db-104">Este método se utiliza en escenarios de editar y continuar para actualizar el almacén de símbolos delta coincidan con el archivo ejecutable portable (PE) original.</span><span class="sxs-lookup"><span data-stu-id="239db-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="239db-105">Es necesario especificar sólo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="239db-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="239db-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="239db-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="239db-107">Si `pIStream` se especifica, el almacén se actualizará con los datos de la <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="239db-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="239db-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="239db-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="239db-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="239db-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="239db-110">[in] El nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="239db-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="239db-111">[in] La secuencia de archivos que se utiliza como una alternativa a la `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="239db-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="239db-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="239db-112">Return Value</span></span>  
 <span data-ttu-id="239db-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="239db-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="239db-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="239db-114">Requirements</span></span>  
 <span data-ttu-id="239db-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="239db-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239db-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="239db-116">See Also</span></span>  
 [<span data-ttu-id="239db-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="239db-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

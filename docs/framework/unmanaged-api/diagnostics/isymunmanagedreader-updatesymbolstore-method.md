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
ms.openlocfilehash: f62c954bf9d73ab564eba388e742794a330362d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080506"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="28f9c-102">ISymUnmanagedReader::UpdateSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="28f9c-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="28f9c-103">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="28f9c-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="28f9c-104">Este método se utiliza en escenarios de editar y continuar para actualizar el almacén de símbolos delta coincidan con el archivo ejecutable portable (PE) original.</span><span class="sxs-lookup"><span data-stu-id="28f9c-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28f9c-105">Es necesario especificar solo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="28f9c-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="28f9c-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="28f9c-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="28f9c-107">Si `pIStream` se especifica, el almacén se actualizará con los datos de la <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="28f9c-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f9c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28f9c-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f9c-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28f9c-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="28f9c-110">[in] El nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="28f9c-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="28f9c-111">[in] La secuencia de archivos que se utiliza como una alternativa a la `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="28f9c-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28f9c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28f9c-112">Return Value</span></span>  
 <span data-ttu-id="28f9c-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="28f9c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f9c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28f9c-114">Requirements</span></span>  
 <span data-ttu-id="28f9c-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28f9c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f9c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="28f9c-116">See also</span></span>

- [<span data-ttu-id="28f9c-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28f9c-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

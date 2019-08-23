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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8721f7c30061fbfd4a761bed090b761762c3c13c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939019"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="b9449-102">ISymUnmanagedReader::ReplaceSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="b9449-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="b9449-103">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="b9449-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="b9449-104">Este método es similar al método [UpdateSymbolStore (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) , salvo que el Delta dado actúa como un reemplazo completo en lugar de una actualización.</span><span class="sxs-lookup"><span data-stu-id="b9449-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9449-105">Solo se debe especificar uno de los `filename` parámetros `pIStream` o, no ambos.</span><span class="sxs-lookup"><span data-stu-id="b9449-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="b9449-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="b9449-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="b9449-107">Si `pIStream` se especifica, el almacén se actualizará con los datos <xref:System.Runtime.InteropServices.ComTypes.IStream>de.</span><span class="sxs-lookup"><span data-stu-id="b9449-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9449-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9449-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9449-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9449-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="b9449-110">de Nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="b9449-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="b9449-111">de El flujo de archivo, que se usa como alternativa `filename` al parámetro.</span><span class="sxs-lookup"><span data-stu-id="b9449-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9449-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9449-112">Return Value</span></span>  
 <span data-ttu-id="b9449-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b9449-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9449-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9449-114">Requirements</span></span>  
 <span data-ttu-id="b9449-115">**Encabezado**: CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b9449-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9449-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9449-116">See also</span></span>

- [<span data-ttu-id="b9449-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9449-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

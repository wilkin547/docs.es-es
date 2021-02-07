---
description: 'Más información acerca de: ISymUnmanagedReader:: Replacesymbolstore ((método)'
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
ms.openlocfilehash: e05344ee0b14d40d735ca3e557c319998daf7849
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763768"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="437bd-103">ISymUnmanagedReader::ReplaceSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="437bd-103">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>

<span data-ttu-id="437bd-104">Reemplaza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="437bd-104">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="437bd-105">Este método es similar al método [UpdateSymbolStore (](isymunmanagedreader-updatesymbolstore-method.md) , salvo que el Delta dado actúa como un reemplazo completo en lugar de una actualización.</span><span class="sxs-lookup"><span data-stu-id="437bd-105">This method is similar to the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="437bd-106">Solo se debe especificar uno de los `filename` `pIStream` parámetros o, no ambos.</span><span class="sxs-lookup"><span data-stu-id="437bd-106">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="437bd-107">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="437bd-107">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="437bd-108">Si `pIStream` se especifica, el almacén se actualizará con los datos de <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="437bd-108">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437bd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="437bd-109">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="437bd-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="437bd-110">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="437bd-111">de Nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="437bd-111">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="437bd-112">de El flujo de archivo, que se usa como alternativa al `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="437bd-112">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="437bd-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="437bd-113">Return Value</span></span>  

 <span data-ttu-id="437bd-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="437bd-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="437bd-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="437bd-115">Requirements</span></span>  

 <span data-ttu-id="437bd-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="437bd-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437bd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="437bd-117">See also</span></span>

- [<span data-ttu-id="437bd-118">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="437bd-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

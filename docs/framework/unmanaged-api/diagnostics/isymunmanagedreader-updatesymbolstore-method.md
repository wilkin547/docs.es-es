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
ms.openlocfilehash: ccc787aa1c820a486d9a513055c9c9834b90bd1a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615441"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="ca00d-102">ISymUnmanagedReader::UpdateSymbolStore (Método)</span><span class="sxs-lookup"><span data-stu-id="ca00d-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="ca00d-103">Actualiza el almacén de símbolos existente con un almacén de símbolos delta.</span><span class="sxs-lookup"><span data-stu-id="ca00d-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="ca00d-104">Este método se usa en escenarios de edición y continuación para actualizar el almacén de símbolos de modo que coincida con las diferencias con el archivo portable ejecutable (PE) original.</span><span class="sxs-lookup"><span data-stu-id="ca00d-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca00d-105">Solo se debe especificar uno de los `filename` `pIStream` parámetros o, no ambos.</span><span class="sxs-lookup"><span data-stu-id="ca00d-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="ca00d-106">Si `filename` se especifica, el almacén de símbolos se actualizará con los símbolos de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="ca00d-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="ca00d-107">Si `pIStream` se especifica, el almacén se actualizará con los datos de <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="ca00d-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca00d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca00d-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca00d-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca00d-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="ca00d-110">de Nombre del archivo que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ca00d-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ca00d-111">de El flujo de archivo, que se usa como alternativa al `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca00d-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca00d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca00d-112">Return Value</span></span>  
 <span data-ttu-id="ca00d-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ca00d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca00d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca00d-114">Requirements</span></span>  
 <span data-ttu-id="ca00d-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ca00d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca00d-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ca00d-116">See also</span></span>

- [<span data-ttu-id="ca00d-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca00d-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

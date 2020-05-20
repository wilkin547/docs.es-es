---
title: ISymUnmanagedWriter::OpenNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: ab248c6a624fbed1a6783383566be093c449ff97
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609890"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="253bd-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="253bd-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="253bd-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="253bd-103">Opens a new namespace.</span></span> <span data-ttu-id="253bd-104">Llame a este método antes de definir métodos o variables que ocupen un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="253bd-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="253bd-105">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="253bd-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="253bd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="253bd-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="253bd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="253bd-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="253bd-108">de Puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="253bd-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="253bd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="253bd-109">Return Value</span></span>  
 <span data-ttu-id="253bd-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="253bd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="253bd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="253bd-111">Requirements</span></span>  
 <span data-ttu-id="253bd-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="253bd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253bd-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="253bd-113">See also</span></span>

- [<span data-ttu-id="253bd-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="253bd-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="253bd-115">Método CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="253bd-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)

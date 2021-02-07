---
description: 'Más información acerca de: ISymUnmanagedWriter:: Opennamespace ((método)'
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
ms.openlocfilehash: ab848e44dfda1f5caaa92bfd3376bdcbd67d8a9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762128"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="8663c-103">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="8663c-103">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="8663c-104">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8663c-104">Opens a new namespace.</span></span> <span data-ttu-id="8663c-105">Llame a este método antes de definir métodos o variables que ocupen un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8663c-105">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="8663c-106">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="8663c-106">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8663c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8663c-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8663c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8663c-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="8663c-109">de Puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8663c-109">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8663c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8663c-110">Return Value</span></span>  

 <span data-ttu-id="8663c-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8663c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8663c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8663c-112">Requirements</span></span>  

 <span data-ttu-id="8663c-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8663c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8663c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8663c-114">See also</span></span>

- [<span data-ttu-id="8663c-115">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8663c-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8663c-116">Método CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="8663c-116">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)

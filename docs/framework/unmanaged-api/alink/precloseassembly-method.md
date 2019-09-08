---
title: PreCloseAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4cf862ae3676b85a7fc3f09a4f5794e01284737
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787237"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="aa0b3-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="aa0b3-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="aa0b3-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-103">Closes the assembly file.</span></span> <span data-ttu-id="aa0b3-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="aa0b3-105">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa0b3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa0b3-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa0b3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa0b3-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="aa0b3-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa0b3-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa0b3-109">Return Value</span></span>  
 <span data-ttu-id="aa0b3-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa0b3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa0b3-111">Requirements</span></span>  
 <span data-ttu-id="aa0b3-112">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="aa0b3-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0b3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa0b3-113">See also</span></span>

- [<span data-ttu-id="aa0b3-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa0b3-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="aa0b3-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa0b3-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="aa0b3-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="aa0b3-116">ALink API</span></span>](index.md)

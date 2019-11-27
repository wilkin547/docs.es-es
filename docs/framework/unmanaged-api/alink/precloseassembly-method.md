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
ms.openlocfilehash: fcfd3e79bbb52837a333b5ffacf5c13ae60f2490
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445615"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="64a60-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="64a60-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="64a60-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64a60-103">Closes the assembly file.</span></span> <span data-ttu-id="64a60-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64a60-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="64a60-105">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="64a60-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a60-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64a60-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="64a60-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64a60-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="64a60-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64a60-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64a60-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64a60-109">Return Value</span></span>  
 <span data-ttu-id="64a60-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="64a60-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a60-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64a60-111">Requirements</span></span>  
 <span data-ttu-id="64a60-112">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="64a60-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a60-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a60-113">See also</span></span>

- [<span data-ttu-id="64a60-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64a60-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="64a60-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64a60-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="64a60-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="64a60-116">ALink API</span></span>](index.md)

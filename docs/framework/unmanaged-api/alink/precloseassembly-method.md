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
ms.openlocfilehash: 31c0c5e23d1a985c2005693e25ca91379037482a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728685"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="c6432-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="c6432-102">PreCloseAssembly Method</span></span>

<span data-ttu-id="c6432-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6432-103">Closes the assembly file.</span></span> <span data-ttu-id="c6432-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6432-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="c6432-105">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="c6432-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6432-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6432-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6432-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6432-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c6432-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c6432-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6432-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6432-109">Return Value</span></span>  

 <span data-ttu-id="c6432-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6432-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6432-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6432-111">Requirements</span></span>  

 <span data-ttu-id="c6432-112">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="c6432-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6432-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6432-113">See also</span></span>

- [<span data-ttu-id="c6432-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6432-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c6432-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6432-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c6432-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="c6432-116">ALink API</span></span>](index.md)

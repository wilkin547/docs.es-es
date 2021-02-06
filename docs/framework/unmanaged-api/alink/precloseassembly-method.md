---
description: 'Más información sobre: método Precloseassembly ('
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
ms.openlocfilehash: 088a5bba654b3442da64672991d76537e9b4722c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662525"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="39453-103">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="39453-103">PreCloseAssembly Method</span></span>

<span data-ttu-id="39453-104">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="39453-104">Closes the assembly file.</span></span> <span data-ttu-id="39453-105">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="39453-105">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="39453-106">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="39453-106">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39453-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39453-107">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="39453-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39453-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="39453-109">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="39453-109">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39453-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39453-110">Return Value</span></span>  

 <span data-ttu-id="39453-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="39453-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39453-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39453-112">Requirements</span></span>  

 <span data-ttu-id="39453-113">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="39453-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39453-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="39453-114">See also</span></span>

- [<span data-ttu-id="39453-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39453-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="39453-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39453-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="39453-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="39453-117">ALink API</span></span>](index.md)

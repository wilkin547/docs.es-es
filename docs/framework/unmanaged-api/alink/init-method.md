---
title: Init (Método)
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726023"
---
# <a name="init-method"></a><span data-ttu-id="7d1c3-102">Init (Método)</span><span class="sxs-lookup"><span data-stu-id="7d1c3-102">Init Method</span></span>

<span data-ttu-id="7d1c3-103">Prepara objetos que implementan la [interfaz ialink (](ialink-interface.md) para su uso.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d1c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d1c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d1c3-105">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="7d1c3-106">Puntero de la [interfaz IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) al dispensador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="7d1c3-107">Puntero de [interfaz imetadataerror (](../metadata/imetadataerror-interface.md) a una interfaz de control de errores opcional.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d1c3-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7d1c3-108">Return Value</span></span>  

 <span data-ttu-id="7d1c3-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d1c3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d1c3-110">Requirements</span></span>  

 <span data-ttu-id="7d1c3-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="7d1c3-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1c3-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d1c3-112">See also</span></span>

- [<span data-ttu-id="7d1c3-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d1c3-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7d1c3-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d1c3-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7d1c3-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7d1c3-115">ALink API</span></span>](index.md)

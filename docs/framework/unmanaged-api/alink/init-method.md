---
title: Método Init
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
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445643"
---
# <a name="init-method"></a><span data-ttu-id="eb5b1-102">Método Init</span><span class="sxs-lookup"><span data-stu-id="eb5b1-102">Init Method</span></span>
<span data-ttu-id="eb5b1-103">Prepara objetos que implementan la [interfaz ialink (](ialink-interface.md) para su uso.</span><span class="sxs-lookup"><span data-stu-id="eb5b1-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb5b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb5b1-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb5b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb5b1-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="eb5b1-106">Puntero de la [interfaz IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) al dispensador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="eb5b1-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="eb5b1-107">Puntero de [interfaz imetadataerror (](../metadata/imetadataerror-interface.md) a una interfaz de control de errores opcional.</span><span class="sxs-lookup"><span data-stu-id="eb5b1-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb5b1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eb5b1-108">Return Value</span></span>  
 <span data-ttu-id="eb5b1-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb5b1-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb5b1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb5b1-110">Requirements</span></span>  
 <span data-ttu-id="eb5b1-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="eb5b1-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5b1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb5b1-112">See also</span></span>

- [<span data-ttu-id="eb5b1-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb5b1-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="eb5b1-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb5b1-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="eb5b1-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="eb5b1-115">ALink API</span></span>](index.md)

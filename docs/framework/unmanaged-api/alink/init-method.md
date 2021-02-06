---
description: 'Más información sobre: método init'
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
ms.openlocfilehash: 531e05a09cbecbfb67c8c004d1e4ba1deb7e59a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662564"
---
# <a name="init-method"></a><span data-ttu-id="f7bd8-103">Init (Método)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-103">Init Method</span></span>

<span data-ttu-id="f7bd8-104">Prepara objetos que implementan la [interfaz ialink (](ialink-interface.md) para su uso.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-104">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7bd8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7bd8-105">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7bd8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7bd8-106">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="f7bd8-107">Puntero de la [interfaz IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) al dispensador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-107">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="f7bd8-108">Puntero de [interfaz imetadataerror (](../metadata/imetadataerror-interface.md) a una interfaz de control de errores opcional.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-108">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7bd8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7bd8-109">Return Value</span></span>  

 <span data-ttu-id="f7bd8-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7bd8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7bd8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7bd8-111">Requirements</span></span>  

 <span data-ttu-id="f7bd8-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="f7bd8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7bd8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7bd8-113">See also</span></span>

- [<span data-ttu-id="f7bd8-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f7bd8-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7bd8-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f7bd8-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f7bd8-116">ALink API</span></span>](index.md)

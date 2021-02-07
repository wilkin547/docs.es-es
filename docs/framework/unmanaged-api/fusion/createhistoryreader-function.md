---
description: 'Más información acerca de: Createhistoryreader ((función)'
title: CreateHistoryReader (Función)
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 0943f3d0f3322d34ed92c0a96b909e4d63ec5e7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761127"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="a24aa-103">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="a24aa-103">CreateHistoryReader Function</span></span>

<span data-ttu-id="a24aa-104">Crea un lector del historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a24aa-104">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a24aa-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a24aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a24aa-106">Parameters</span></span>  

 `wzFilePath`  
 <span data-ttu-id="a24aa-107">de Ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="a24aa-107">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="a24aa-108">enuncia Cuando se completa correctamente, contiene un puntero al lector del historial.</span><span class="sxs-lookup"><span data-stu-id="a24aa-108">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a24aa-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a24aa-109">Return Value</span></span>  

 <span data-ttu-id="a24aa-110">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a24aa-110">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="a24aa-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="a24aa-111">Return code</span></span>|<span data-ttu-id="a24aa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a24aa-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a24aa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a24aa-113">S_OK</span></span>|<span data-ttu-id="a24aa-114">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a24aa-114">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="a24aa-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a24aa-115">E_INVALIDARG</span></span>|<span data-ttu-id="a24aa-116">Indica que `wzFilePath` o `ppHistoryReader` están establecidos en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="a24aa-116">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a24aa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a24aa-117">Requirements</span></span>  

 <span data-ttu-id="a24aa-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a24aa-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24aa-119">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="a24aa-119">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="a24aa-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24aa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24aa-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a24aa-121">See also</span></span>

- [<span data-ttu-id="a24aa-122">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="a24aa-122">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

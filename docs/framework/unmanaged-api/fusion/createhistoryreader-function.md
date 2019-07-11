---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee30d4f32e05fab27ae70052b28d3d152594cf90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778414"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="3327a-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="3327a-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="3327a-103">Crea un lector de historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3327a-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3327a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3327a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3327a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3327a-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="3327a-106">[in] La ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="3327a-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="3327a-107">[out] Se completa correctamente, contiene un puntero al lector de historial.</span><span class="sxs-lookup"><span data-stu-id="3327a-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3327a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3327a-108">Return Value</span></span>  
 <span data-ttu-id="3327a-109">Este método devuelve códigos de error COM estándar definidos en WinError.h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3327a-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="3327a-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="3327a-110">Return code</span></span>|<span data-ttu-id="3327a-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3327a-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3327a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3327a-112">S_OK</span></span>|<span data-ttu-id="3327a-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3327a-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="3327a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3327a-114">E_INVALIDARG</span></span>|<span data-ttu-id="3327a-115">Indica que `wzFilePath` o `ppHistoryReader` se establecen en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="3327a-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3327a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3327a-116">Requirements</span></span>  
 <span data-ttu-id="3327a-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3327a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3327a-118">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="3327a-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="3327a-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3327a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3327a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3327a-120">See also</span></span>

- [<span data-ttu-id="3327a-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3327a-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

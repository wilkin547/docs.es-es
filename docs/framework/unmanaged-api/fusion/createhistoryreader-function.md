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
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132267"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="4863b-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="4863b-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="4863b-103">Crea un lector de historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="4863b-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4863b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4863b-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4863b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4863b-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="4863b-106">[in] La ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="4863b-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="4863b-107">[out] Se completa correctamente, contiene un puntero al lector de historial.</span><span class="sxs-lookup"><span data-stu-id="4863b-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4863b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4863b-108">Return Value</span></span>  
 <span data-ttu-id="4863b-109">Este método devuelve códigos de error COM estándar definidos en WinError.h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4863b-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="4863b-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="4863b-110">Return code</span></span>|<span data-ttu-id="4863b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4863b-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4863b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4863b-112">S_OK</span></span>|<span data-ttu-id="4863b-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4863b-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="4863b-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4863b-114">E_INVALIDARG</span></span>|<span data-ttu-id="4863b-115">Indica que `wzFilePath` o `ppHistoryReader` se establecen en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="4863b-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4863b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4863b-116">Requirements</span></span>  
 <span data-ttu-id="4863b-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4863b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4863b-118">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="4863b-118">**Library:** Fusion.dll</span></span>  
  
 **<span data-ttu-id="4863b-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4863b-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4863b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4863b-120">See also</span></span>

- [<span data-ttu-id="4863b-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="4863b-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

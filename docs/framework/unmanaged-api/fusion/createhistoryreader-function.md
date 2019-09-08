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
ms.openlocfilehash: 2710d14d6e73879fd17a6b58659463ea205f2384
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795368"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="535ef-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="535ef-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="535ef-103">Crea un lector del historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="535ef-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="535ef-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="535ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="535ef-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="535ef-106">de Ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="535ef-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="535ef-107">enuncia Cuando se completa correctamente, contiene un puntero al lector del historial.</span><span class="sxs-lookup"><span data-stu-id="535ef-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="535ef-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="535ef-108">Return Value</span></span>  
 <span data-ttu-id="535ef-109">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="535ef-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="535ef-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="535ef-110">Return code</span></span>|<span data-ttu-id="535ef-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="535ef-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="535ef-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="535ef-112">S_OK</span></span>|<span data-ttu-id="535ef-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="535ef-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="535ef-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="535ef-114">E_INVALIDARG</span></span>|<span data-ttu-id="535ef-115">Indica que `wzFilePath` o `ppHistoryReader` están establecidos en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="535ef-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="535ef-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="535ef-116">Requirements</span></span>  
 <span data-ttu-id="535ef-117">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="535ef-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="535ef-118">**Biblioteca** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="535ef-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="535ef-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="535ef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535ef-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="535ef-120">See also</span></span>

- [<span data-ttu-id="535ef-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="535ef-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

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
ms.openlocfilehash: 9dae3f1403d33aaf3cfb87d17856640548a90b4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688983"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="f4713-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="f4713-102">CreateHistoryReader Function</span></span>

<span data-ttu-id="f4713-103">Crea un lector del historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f4713-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4713-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4713-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4713-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4713-105">Parameters</span></span>  

 `wzFilePath`  
 <span data-ttu-id="f4713-106">de Ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="f4713-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="f4713-107">enuncia Cuando se completa correctamente, contiene un puntero al lector del historial.</span><span class="sxs-lookup"><span data-stu-id="f4713-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4713-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4713-108">Return Value</span></span>  

 <span data-ttu-id="f4713-109">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4713-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="f4713-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="f4713-110">Return code</span></span>|<span data-ttu-id="f4713-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4713-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f4713-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4713-112">S_OK</span></span>|<span data-ttu-id="f4713-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4713-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="f4713-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f4713-114">E_INVALIDARG</span></span>|<span data-ttu-id="f4713-115">Indica que `wzFilePath` o `ppHistoryReader` están establecidos en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="f4713-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4713-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4713-116">Requirements</span></span>  

 <span data-ttu-id="f4713-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4713-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4713-118">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="f4713-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="f4713-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4713-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4713-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4713-120">See also</span></span>

- [<span data-ttu-id="f4713-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="f4713-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

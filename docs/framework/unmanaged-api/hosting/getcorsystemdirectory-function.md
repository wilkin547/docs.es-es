---
title: GetCORSystemDirectory (Función)
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 21b01156afceb24ab5c132894fae6922d7b97e59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733300"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="7c8d8-102">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="7c8d8-102">GetCORSystemDirectory Function</span></span>

<span data-ttu-id="7c8d8-103">Devuelve el directorio de instalación del Common Language Runtime (CLR) que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="7c8d8-104">El directorio de instalación es completo, por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="7c8d8-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="7c8d8-105">Esta función es desusada.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-105">This function is deprecated.</span></span> <span data-ttu-id="7c8d8-106">Se sustituye por el método [ICLRRuntimeInfo:: GetRuntimeDirectory (](iclrruntimeinfo-getruntimedirectory-method.md) proporcionado en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8d8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c8d8-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="7c8d8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c8d8-108">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="7c8d8-109">enuncia Búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="7c8d8-110">Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7c8d8-111">de Tamaño, en bytes, de `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="7c8d8-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7c8d8-112">enuncia Número de caracteres devueltos en `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="7c8d8-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c8d8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c8d8-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7c8d8-114">No utilice esta función en los procesos que ejecutan la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="7c8d8-115">Si hay instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8d8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c8d8-116">Requirements</span></span>  

 <span data-ttu-id="7c8d8-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c8d8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8d8-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7c8d8-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c8d8-119">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c8d8-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c8d8-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8d8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8d8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c8d8-121">See also</span></span>

- [<span data-ttu-id="7c8d8-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="7c8d8-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)

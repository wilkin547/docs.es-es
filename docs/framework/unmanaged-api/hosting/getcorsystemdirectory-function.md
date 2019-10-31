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
ms.openlocfilehash: 63fb505a92683fda21b6e71a6ca891ca35afba1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136413"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="43306-102">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="43306-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="43306-103">Devuelve el directorio de instalación del Common Language Runtime (CLR) que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="43306-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="43306-104">El directorio de instalación es completo, por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="43306-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="43306-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="43306-105">This function is deprecated.</span></span> <span data-ttu-id="43306-106">Se sustituye por el método [ICLRRuntimeInfo:: GetRuntimeDirectory (](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) proporcionado en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="43306-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43306-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43306-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="43306-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43306-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="43306-109">enuncia Búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="43306-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="43306-110">Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="43306-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="43306-111">de Tamaño, en bytes, de `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="43306-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="43306-112">enuncia Número de caracteres devueltos en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="43306-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43306-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43306-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="43306-114">No utilice esta función en los procesos que ejecutan la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="43306-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="43306-115">Si hay instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.</span><span class="sxs-lookup"><span data-stu-id="43306-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43306-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43306-116">Requirements</span></span>  
 <span data-ttu-id="43306-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43306-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43306-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43306-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43306-119">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="43306-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43306-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43306-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43306-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="43306-121">See also</span></span>

- [<span data-ttu-id="43306-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="43306-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

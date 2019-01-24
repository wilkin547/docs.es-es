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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8608a5438b31cad64bb27d2866109f479dad441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739503"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="7d718-102">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="7d718-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="7d718-103">Devuelve el directorio de instalación de common language runtime (CLR) que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7d718-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="7d718-104">El directorio de instalación se completa, por ejemplo, "c:\windows\microsoft.net\framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="7d718-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="7d718-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="7d718-105">This function is deprecated.</span></span> <span data-ttu-id="7d718-106">Sustituida por la [GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) método proporcionado en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d718-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d718-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d718-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d718-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d718-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="7d718-109">[out] Un búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7d718-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="7d718-110">Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7d718-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7d718-111">[in] El tamaño, en bytes, de `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="7d718-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7d718-112">[out] El número de caracteres devuelto en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="7d718-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d718-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d718-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7d718-114">No use esta función en procesos que se ejecutan la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="7d718-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="7d718-115">Si está instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.</span><span class="sxs-lookup"><span data-stu-id="7d718-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d718-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d718-116">Requirements</span></span>  
 <span data-ttu-id="7d718-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d718-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d718-118">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d718-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d718-119">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d718-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d718-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d718-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d718-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d718-121">See also</span></span>
- [<span data-ttu-id="7d718-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="7d718-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

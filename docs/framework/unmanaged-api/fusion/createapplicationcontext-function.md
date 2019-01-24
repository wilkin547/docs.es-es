---
title: CreateApplicationContext (Función)
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 709769c336d875ee5ddd00b4e1cf919c61e2c394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746627"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="9b97b-102">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="9b97b-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="9b97b-103">Esta función admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="9b97b-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b97b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b97b-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b97b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b97b-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="9b97b-106">[in] Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="9b97b-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="9b97b-107">[out] Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b97b-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b97b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b97b-108">Requirements</span></span>  
 <span data-ttu-id="9b97b-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b97b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b97b-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9b97b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9b97b-111">**Biblioteca:** Incluye como recurso en el archivo Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="9b97b-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="9b97b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b97b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b97b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b97b-113">See also</span></span>
- [<span data-ttu-id="9b97b-114">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b97b-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="9b97b-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="9b97b-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="9b97b-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="9b97b-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

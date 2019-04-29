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
ms.openlocfilehash: d98829b29100824e5d606e23aaf287c9f6e81d69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771922"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="a0a68-102">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="a0a68-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="a0a68-103">Esta función admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="a0a68-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0a68-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0a68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0a68-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="a0a68-106">[in] Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="a0a68-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="a0a68-107">[out] Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0a68-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a68-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0a68-108">Requirements</span></span>  
 <span data-ttu-id="a0a68-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0a68-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a68-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a0a68-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a0a68-111">**Biblioteca:** Incluye como recurso en el archivo Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="a0a68-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="a0a68-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a68-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a68-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0a68-113">See also</span></span>

- [<span data-ttu-id="a0a68-114">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0a68-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="a0a68-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="a0a68-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="a0a68-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="a0a68-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)

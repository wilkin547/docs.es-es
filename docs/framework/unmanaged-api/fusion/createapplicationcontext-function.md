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
ms.openlocfilehash: 9418be85f5b72bac8eed7f5ea4af4fc42439b01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683241"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="68687-102">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="68687-102">CreateApplicationContext Function</span></span>

<span data-ttu-id="68687-103">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="68687-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68687-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68687-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="68687-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68687-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="68687-106">de Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="68687-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="68687-107">enuncia Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68687-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68687-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68687-108">Requirements</span></span>  

 <span data-ttu-id="68687-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68687-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68687-110">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="68687-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="68687-111">**Biblioteca:** Se incluye como un recurso en Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="68687-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="68687-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68687-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68687-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68687-113">See also</span></span>

- [<span data-ttu-id="68687-114">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="68687-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="68687-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="68687-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="68687-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="68687-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)

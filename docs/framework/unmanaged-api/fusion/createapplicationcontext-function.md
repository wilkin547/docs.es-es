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
ms.openlocfilehash: e188fe80e770481aac02244a2c105639e4da19e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108890"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="627ba-102">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="627ba-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="627ba-103">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="627ba-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="627ba-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="627ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="627ba-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="627ba-106">de Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="627ba-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="627ba-107">enuncia Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="627ba-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="627ba-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="627ba-108">Requirements</span></span>  
 <span data-ttu-id="627ba-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="627ba-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="627ba-110">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="627ba-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="627ba-111">**Biblioteca:** Se incluye como un recurso en Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="627ba-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="627ba-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="627ba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627ba-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="627ba-113">See also</span></span>

- [<span data-ttu-id="627ba-114">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="627ba-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="627ba-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="627ba-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="627ba-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="627ba-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)

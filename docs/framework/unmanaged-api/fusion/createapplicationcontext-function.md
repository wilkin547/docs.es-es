---
description: 'Más información acerca de: Createapplicationcontext ((función)'
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
ms.openlocfilehash: f192e1ccc371cb6d50e4a41a286c412825ee4181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761189"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="ca77d-103">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="ca77d-103">CreateApplicationContext Function</span></span>

<span data-ttu-id="ca77d-104">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="ca77d-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca77d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca77d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca77d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca77d-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="ca77d-107">de Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="ca77d-107">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="ca77d-108">enuncia Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca77d-108">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca77d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca77d-109">Requirements</span></span>  

 <span data-ttu-id="ca77d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca77d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca77d-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ca77d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ca77d-112">**Biblioteca:** Se incluye como un recurso en Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="ca77d-112">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="ca77d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca77d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca77d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca77d-114">See also</span></span>

- [<span data-ttu-id="ca77d-115">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca77d-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="ca77d-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="ca77d-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="ca77d-117">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="ca77d-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)

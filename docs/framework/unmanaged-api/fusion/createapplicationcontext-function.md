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
ms.openlocfilehash: 25364330dafdf858c4b41e9a05731c37e97fbb57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795433"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="67ac3-102">CreateApplicationContext (Función)</span><span class="sxs-lookup"><span data-stu-id="67ac3-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="67ac3-103">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="67ac3-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ac3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67ac3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="67ac3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67ac3-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="67ac3-106">de Un puntero a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="67ac3-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="67ac3-107">enuncia Un puntero a un contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67ac3-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67ac3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67ac3-108">Requirements</span></span>  
 <span data-ttu-id="67ac3-109">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ac3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ac3-110">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="67ac3-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="67ac3-111">**Biblioteca** Se incluye como un recurso en Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="67ac3-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="67ac3-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ac3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ac3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="67ac3-113">See also</span></span>

- [<span data-ttu-id="67ac3-114">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67ac3-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="67ac3-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="67ac3-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="67ac3-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="67ac3-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)

---
title: CreateInstallReferenceEnum (Función)
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795393"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="2fac8-102">CreateInstallReferenceEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="2fac8-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="2fac8-103">Obtiene un puntero a una instancia de [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) que representa una lista de referencias de una aplicación al ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="2fac8-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fac8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fac8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fac8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fac8-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="2fac8-106">enuncia Puntero devuelto `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="2fac8-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="2fac8-107">de La [IAssemblyName](iassemblyname-interface.md) que identifica el ensamblado para el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="2fac8-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2fac8-108">de Marcas que influyen en el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="2fac8-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="2fac8-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="2fac8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2fac8-110">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="2fac8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fac8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fac8-111">Requirements</span></span>  
 <span data-ttu-id="2fac8-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fac8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fac8-113">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2fac8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2fac8-114">**Biblioteca** Fusion. dll y mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="2fac8-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2fac8-115">Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2fac8-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2fac8-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fac8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fac8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fac8-117">See also</span></span>

- [<span data-ttu-id="2fac8-118">IInstallReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fac8-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="2fac8-119">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fac8-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2fac8-120">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="2fac8-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

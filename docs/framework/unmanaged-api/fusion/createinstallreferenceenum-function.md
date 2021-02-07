---
description: 'Más información acerca de: Createinstallreferenceenum ((función)'
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
ms.openlocfilehash: cc7551707cb46bcf0c475a0095684dbc790836e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761158"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="9215a-103">CreateInstallReferenceEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="9215a-103">CreateInstallReferenceEnum Function</span></span>

<span data-ttu-id="9215a-104">Obtiene un puntero a una instancia de [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) que representa una lista de referencias de una aplicación al ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="9215a-104">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9215a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9215a-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9215a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9215a-106">Parameters</span></span>  

 `ppRefEnum`  
 <span data-ttu-id="9215a-107">enuncia Puntero devuelto `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="9215a-107">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="9215a-108">de La [IAssemblyName](iassemblyname-interface.md) que identifica el ensamblado para el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="9215a-108">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9215a-109">de Marcas que influyen en el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="9215a-109">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="9215a-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="9215a-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9215a-111">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="9215a-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9215a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9215a-112">Requirements</span></span>  

 <span data-ttu-id="9215a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9215a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9215a-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9215a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9215a-115">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="9215a-115">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="9215a-116">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9215a-116">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9215a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9215a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9215a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9215a-118">See also</span></span>

- [<span data-ttu-id="9215a-119">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9215a-119">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="9215a-120">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9215a-120">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9215a-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="9215a-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

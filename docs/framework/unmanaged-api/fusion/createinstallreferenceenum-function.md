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
ms.openlocfilehash: 0f62b05ebbd8b27dba160c8281c1d40748c90fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688840"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="2ff8a-102">CreateInstallReferenceEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="2ff8a-102">CreateInstallReferenceEnum Function</span></span>

<span data-ttu-id="2ff8a-103">Obtiene un puntero a una instancia de [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) que representa una lista de referencias de una aplicación al ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ff8a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ff8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ff8a-105">Parameters</span></span>  

 `ppRefEnum`  
 <span data-ttu-id="2ff8a-106">enuncia Puntero devuelto `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="2ff8a-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="2ff8a-107">de La [IAssemblyName](iassemblyname-interface.md) que identifica el ensamblado para el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2ff8a-108">de Marcas que influyen en el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="2ff8a-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2ff8a-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff8a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ff8a-111">Requirements</span></span>  

 <span data-ttu-id="2ff8a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff8a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff8a-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2ff8a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2ff8a-114">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2ff8a-115">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ff8a-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2ff8a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff8a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ff8a-117">See also</span></span>

- [<span data-ttu-id="2ff8a-118">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ff8a-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="2ff8a-119">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ff8a-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2ff8a-120">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="2ff8a-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

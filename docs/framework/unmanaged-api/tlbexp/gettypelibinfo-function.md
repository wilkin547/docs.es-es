---
title: GetTypeLibInfo (Función)
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: 4c630f5f7e3dc66ce44f10cd69fcd108226b0250
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554337"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="15945-102">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="15945-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="15945-103">Devuelve información sobre la biblioteca de tipos especificada examinando su estructura [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="15945-103">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15945-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15945-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15945-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15945-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="15945-106">de Nombre de archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="15945-107">enuncia GUID de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="15945-108">enuncia IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="15945-109">enuncia Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el sistema operativo de destino de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-109">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="15945-110">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="15945-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="15945-111">enuncia Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="15945-112">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="15945-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="15945-113">enuncia Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="15945-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="15945-114">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="15945-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15945-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15945-115">Remarks</span></span>  
 <span data-ttu-id="15945-116">El `GetTypeLibInfo` [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md)llama a la función.</span><span class="sxs-lookup"><span data-stu-id="15945-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="15945-117">Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="15945-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="15945-118">Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER` .</span><span class="sxs-lookup"><span data-stu-id="15945-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="15945-119">En caso contrario, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="15945-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15945-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15945-120">Requirements</span></span>  
 <span data-ttu-id="15945-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15945-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15945-122">**Encabezado:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="15945-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="15945-123">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="15945-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="15945-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15945-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15945-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="15945-125">See also</span></span>

- [<span data-ttu-id="15945-126">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="15945-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="15945-127">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="15945-127">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

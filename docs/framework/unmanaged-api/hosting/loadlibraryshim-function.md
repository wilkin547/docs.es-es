---
title: LoadLibraryShim (Función)
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: 11bb220068e978dc130701e3b28ab3f421be7337
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937653"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="e0581-102">LoadLibraryShim (Función)</span><span class="sxs-lookup"><span data-stu-id="e0581-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="e0581-103">Carga una versión especificada de una DLL incluida en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0581-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="e0581-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e0581-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="e0581-105">Use en su lugar el método [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0581-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0581-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0581-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0581-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="e0581-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="e0581-108">de Cadena terminada en cero que representa el nombre del archivo DLL que se va a cargar desde la biblioteca de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0581-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="e0581-109">de Cadena terminada en cero que representa la versión de la DLL que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="e0581-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="e0581-110">Si `szVersion` es null, la versión seleccionada para cargar es la versión más reciente del archivo DLL especificado que es anterior a la versión 4.</span><span class="sxs-lookup"><span data-stu-id="e0581-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="e0581-111">Es decir, todas las versiones iguales o posteriores a la versión 4 se omiten si `szVersion` es null, y si no se instala ninguna versión anterior a la versión 4, la DLL no se carga.</span><span class="sxs-lookup"><span data-stu-id="e0581-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="e0581-112">Esto se hace para asegurarse de que la instalación de .NET Framework 4 no afecte a las aplicaciones o componentes preexistentes.</span><span class="sxs-lookup"><span data-stu-id="e0581-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="e0581-113">Vea la entrada [en proceso SxS y inicio rápido de migración](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) en el blog del equipo de CLR.</span><span class="sxs-lookup"><span data-stu-id="e0581-113">See the entry [In-Proc SxS and Migration Quick Start](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e0581-114">Reservado para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="e0581-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="e0581-115">enuncia Puntero al identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="e0581-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0581-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0581-116">Return Value</span></span>  
 <span data-ttu-id="e0581-117">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0581-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="e0581-118">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="e0581-118">Return code</span></span>|<span data-ttu-id="e0581-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0581-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e0581-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0581-120">S_OK</span></span>|<span data-ttu-id="e0581-121">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0581-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="e0581-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="e0581-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="e0581-123">La carga de `szDllName` requiere cargar el Common Language Runtime (CLR) y no se puede cargar la versión necesaria de CLR.</span><span class="sxs-lookup"><span data-stu-id="e0581-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0581-124">Notas</span><span class="sxs-lookup"><span data-stu-id="e0581-124">Remarks</span></span>  
 <span data-ttu-id="e0581-125">Esta función se usa para cargar los archivos DLL que se incluyen en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0581-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="e0581-126">No carga los archivos dll generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e0581-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0581-127">A partir de la versión .NET Framework 2,0, la carga de Fusion. dll hace que se cargue el CLR.</span><span class="sxs-lookup"><span data-stu-id="e0581-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="e0581-128">Esto se debe a que las funciones de Fusion. dll son ahora contenedores cuyas implementaciones son proporcionadas por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0581-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0581-129">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e0581-129">Requirements</span></span>  
 <span data-ttu-id="e0581-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0581-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0581-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e0581-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0581-132">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0581-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0581-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0581-133">See also</span></span>

- [<span data-ttu-id="e0581-134">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e0581-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

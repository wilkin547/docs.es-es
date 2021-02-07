---
description: 'Más información acerca de: enumeración METAHOST_POLICY_FLAGS'
title: METAHOST_POLICY_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: 3a3ebe602c8f048b7f9fc907f5d4741722bd0ed3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679628"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="bebc2-103">METAHOST_POLICY_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bebc2-103">METAHOST_POLICY_FLAGS Enumeration</span></span>

<span data-ttu-id="bebc2-104">Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bebc2-104">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="bebc2-105">Esta enumeración la usa el método [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bebc2-105">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bebc2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bebc2-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bebc2-107">Members</span><span class="sxs-lookup"><span data-stu-id="bebc2-107">Members</span></span>  
  
|<span data-ttu-id="bebc2-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="bebc2-108">Member</span></span>|<span data-ttu-id="bebc2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bebc2-109">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="bebc2-110">Define la Directiva de alta compatibilidad, que no tiene en cuenta ningún Common Language Runtime (CLR) que se cargue en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="bebc2-110">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="bebc2-111">En su lugar, solo tiene en cuenta el CLR instalado y las preferencias del componente, como se derivan del propio archivo de ensamblado, la versión de compilación compilada declarada o el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bebc2-111">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="bebc2-112">Aplica la Directiva de actualización al resultado del enlace de la versión cuando no se encuentra una coincidencia exacta, en función del contenido de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\ . NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="bebc2-112">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="bebc2-113">Esto tiene el mismo efecto que [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bebc2-113">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="bebc2-114">Se devuelven los resultados de enlace como si la imagen proporcionada a la llamada se iniciara en un nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="bebc2-114">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="bebc2-115">Actualmente, `GetRequestedRuntime` omite el conjunto de tiempos de ejecución cargables y enlaces con el conjunto de tiempos de ejecución instalados.</span><span class="sxs-lookup"><span data-stu-id="bebc2-115">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="bebc2-116">Esta marca permite a un host determinar en qué tiempo de ejecución se enlazará un archivo EXE cuando se inicie.</span><span class="sxs-lookup"><span data-stu-id="bebc2-116">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="bebc2-117">Se muestra un cuadro de diálogo de error si `GetRequestedRuntime` no puede encontrar un tiempo de ejecución que sea compatible con los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="bebc2-117">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="bebc2-118">A partir de la .NET Framework 4,5, este cuadro de diálogo de error puede adoptar la forma de un cuadro de diálogo de característica de Windows que pregunta si el usuario desea habilitar la característica adecuada.</span><span class="sxs-lookup"><span data-stu-id="bebc2-118">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="bebc2-119">`GetRequestedRuntime` usa la imagen de proceso (y cualquier archivo de configuración correspondiente) como entrada adicional para el proceso de enlace.</span><span class="sxs-lookup"><span data-stu-id="bebc2-119">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="bebc2-120">De forma predeterminada, `GetRequestedRuntime` no revierte a la ruta de acceso de la imagen de proceso (normalmente, el archivo exe que se usó para iniciar el proceso) al determinar el Runtime con el que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="bebc2-120">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="bebc2-121">`GetRequestedRuntime` debe comprobar si la SKU adecuada está instalada cuando no haya información disponible en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bebc2-121">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="bebc2-122">Esto permite que las aplicaciones que no tienen archivos de configuración no funcionen correctamente en SKU más pequeñas que la instalación predeterminada del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bebc2-122">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="bebc2-123">De forma predeterminada, no `GetRequestedRuntime` comprueba si se instala la SKU adecuada a menos que se especifique el atributo SKU en el elemento de archivo de configuración `<supportedRuntime />` .</span><span class="sxs-lookup"><span data-stu-id="bebc2-123">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="bebc2-124">`GetRequestedRuntime` debe omitir SEM_FAILCRITICALERRORS (que se establece mediante una llamada a la función [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) ) y mostrar el cuadro de diálogo de error.</span><span class="sxs-lookup"><span data-stu-id="bebc2-124">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="bebc2-125">De forma predeterminada, SEM_FAILCRITICALERRORS suprime el cuadro de diálogo de error.</span><span class="sxs-lookup"><span data-stu-id="bebc2-125">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="bebc2-126">Es posible que se haya heredado de otro proceso y que el error silencioso no sea deseable en el escenario.</span><span class="sxs-lookup"><span data-stu-id="bebc2-126">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bebc2-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bebc2-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bebc2-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bebc2-128">Requirements</span></span>  

 <span data-ttu-id="bebc2-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bebc2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bebc2-130">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="bebc2-130">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="bebc2-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bebc2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bebc2-132">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bebc2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebc2-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bebc2-133">See also</span></span>

- [<span data-ttu-id="bebc2-134">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="bebc2-134">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="bebc2-135">Método GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="bebc2-135">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)

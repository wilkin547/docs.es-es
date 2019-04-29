---
title: <disableCommitThreadStack> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08ffd6ffcb9a8fa356d486f6d2ae1113de0fa682
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674225"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="9ac7a-102">\<disableCommitThreadStack > elemento</span><span class="sxs-lookup"><span data-stu-id="9ac7a-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="9ac7a-103">Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="9ac7a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9ac7a-104">\<configuration></span></span>  
<span data-ttu-id="9ac7a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9ac7a-105">\<runtime></span></span>  
<span data-ttu-id="9ac7a-106">\<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="9ac7a-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac7a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ac7a-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ac7a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ac7a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9ac7a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ac7a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ac7a-110">Attributes</span></span>  
  
|<span data-ttu-id="9ac7a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ac7a-111">Attribute</span></span>|<span data-ttu-id="9ac7a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ac7a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ac7a-113">enabled</span><span class="sxs-lookup"><span data-stu-id="9ac7a-113">enabled</span></span>|<span data-ttu-id="9ac7a-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ac7a-115">Especifica si la confirmación de la pila de subprocesos completa cuando se inicia el subproceso (comportamiento predeterminado) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9ac7a-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="9ac7a-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="9ac7a-117">Valor</span><span class="sxs-lookup"><span data-stu-id="9ac7a-117">Value</span></span>|<span data-ttu-id="9ac7a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ac7a-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ac7a-119">0</span><span class="sxs-lookup"><span data-stu-id="9ac7a-119">0</span></span>|<span data-ttu-id="9ac7a-120">No deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="9ac7a-121">1</span><span class="sxs-lookup"><span data-stu-id="9ac7a-121">1</span></span>|<span data-ttu-id="9ac7a-122">Deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ac7a-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ac7a-123">Child Elements</span></span>  
 <span data-ttu-id="9ac7a-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ac7a-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ac7a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9ac7a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ac7a-126">Element</span></span>|<span data-ttu-id="9ac7a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ac7a-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ac7a-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ac7a-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="9ac7a-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac7a-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ac7a-130">Remarks</span></span>  
 <span data-ttu-id="9ac7a-131">El comportamiento predeterminado de Common Language Runtime consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="9ac7a-132">Si se debe crear un gran número de subprocesos en un servidor con memoria limitada y la mayoría de estos subprocesos usarán muy poco espacio de pila, el servidor mejorará su rendimiento si Common Language Runtime no confirma la pila de subprocesos completa inmediatamente cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ac7a-133">Los hosts no administrados pueden usar la marca de inicio `STARTUP_DISABLE_COMMITTHREADSTACK` en la enumeración [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ac7a-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ac7a-134">Example</span></span>  
 <span data-ttu-id="9ac7a-135">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ac7a-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ac7a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ac7a-136">See also</span></span>

- [<span data-ttu-id="9ac7a-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="9ac7a-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9ac7a-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9ac7a-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

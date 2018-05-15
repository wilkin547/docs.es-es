---
title: '&lt;disableCommitThreadStack&gt; elemento'
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
ms.openlocfilehash: 4d8724d16a25cdec040fa5b1f5472da06b11f669
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdisablecommitthreadstackgt-element"></a><span data-ttu-id="bdccb-102">&lt;disableCommitThreadStack&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="bdccb-102">&lt;disableCommitThreadStack&gt; Element</span></span>
<span data-ttu-id="bdccb-103">Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="bdccb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bdccb-104">\<configuration></span></span>  
<span data-ttu-id="bdccb-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="bdccb-105">\<runtime></span></span>  
<span data-ttu-id="bdccb-106">\<disableCommitThreadStack ></span><span class="sxs-lookup"><span data-stu-id="bdccb-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdccb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdccb-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdccb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdccb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bdccb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdccb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdccb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdccb-110">Attributes</span></span>  
  
|<span data-ttu-id="bdccb-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdccb-111">Attribute</span></span>|<span data-ttu-id="bdccb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdccb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdccb-113">enabled</span><span class="sxs-lookup"><span data-stu-id="bdccb-113">enabled</span></span>|<span data-ttu-id="bdccb-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bdccb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdccb-115">Especifica si la confirmación de la pila de subprocesos completa cuando se inicia el subproceso (comportamiento predeterminado) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="bdccb-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bdccb-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="bdccb-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="bdccb-117">Valor</span><span class="sxs-lookup"><span data-stu-id="bdccb-117">Value</span></span>|<span data-ttu-id="bdccb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdccb-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdccb-119">0</span><span class="sxs-lookup"><span data-stu-id="bdccb-119">0</span></span>|<span data-ttu-id="bdccb-120">No deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="bdccb-121">1</span><span class="sxs-lookup"><span data-stu-id="bdccb-121">1</span></span>|<span data-ttu-id="bdccb-122">Deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdccb-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdccb-123">Child Elements</span></span>  
 <span data-ttu-id="bdccb-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bdccb-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdccb-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdccb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bdccb-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdccb-126">Element</span></span>|<span data-ttu-id="bdccb-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdccb-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdccb-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bdccb-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="bdccb-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bdccb-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdccb-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdccb-130">Remarks</span></span>  
 <span data-ttu-id="bdccb-131">El comportamiento predeterminado de Common Language Runtime consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="bdccb-132">Si se debe crear un gran número de subprocesos en un servidor con memoria limitada y la mayoría de estos subprocesos usarán muy poco espacio de pila, el servidor mejorará su rendimiento si Common Language Runtime no confirma la pila de subprocesos completa inmediatamente cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdccb-133">Los hosts no administrados pueden usar la marca de inicio `STARTUP_DISABLE_COMMITTHREADSTACK` en la enumeración [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="bdccb-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdccb-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdccb-134">Example</span></span>  
 <span data-ttu-id="bdccb-135">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdccb-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdccb-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdccb-136">See Also</span></span>  
 [<span data-ttu-id="bdccb-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bdccb-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="bdccb-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bdccb-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

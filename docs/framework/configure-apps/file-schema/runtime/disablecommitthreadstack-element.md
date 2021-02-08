---
description: 'Más información acerca de: <disableCommitThreadStack> elemento'
title: <disableCommitThreadStack> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: f80a23b12f67b9f3df1ddb010edb735225f6f7a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787102"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="10ad8-103">\<disableCommitThreadStack> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="10ad8-103">\<disableCommitThreadStack> Element</span></span>

<span data-ttu-id="10ad8-104">Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-104">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="10ad8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10ad8-105">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10ad8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10ad8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="10ad8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10ad8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10ad8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="10ad8-108">Attributes</span></span>  
  
|<span data-ttu-id="10ad8-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="10ad8-109">Attribute</span></span>|<span data-ttu-id="10ad8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="10ad8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10ad8-111">enabled</span><span class="sxs-lookup"><span data-stu-id="10ad8-111">enabled</span></span>|<span data-ttu-id="10ad8-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="10ad8-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="10ad8-113">Especifica si la confirmación de la pila de subprocesos completa cuando se inicia el subproceso (comportamiento predeterminado) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="10ad8-113">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="10ad8-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="10ad8-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="10ad8-115">Value</span><span class="sxs-lookup"><span data-stu-id="10ad8-115">Value</span></span>|<span data-ttu-id="10ad8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="10ad8-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="10ad8-117">0</span><span class="sxs-lookup"><span data-stu-id="10ad8-117">0</span></span>|<span data-ttu-id="10ad8-118">No deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-118">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="10ad8-119">1</span><span class="sxs-lookup"><span data-stu-id="10ad8-119">1</span></span>|<span data-ttu-id="10ad8-120">Deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-120">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10ad8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10ad8-121">Child Elements</span></span>  

 <span data-ttu-id="10ad8-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="10ad8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10ad8-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10ad8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="10ad8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="10ad8-124">Element</span></span>|<span data-ttu-id="10ad8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="10ad8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10ad8-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10ad8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10ad8-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10ad8-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10ad8-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10ad8-128">Remarks</span></span>  

 <span data-ttu-id="10ad8-129">El comportamiento predeterminado de Common Language Runtime consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-129">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="10ad8-130">Si se debe crear un gran número de subprocesos en un servidor con memoria limitada y la mayoría de estos subprocesos usarán muy poco espacio de pila, el servidor mejorará su rendimiento si Common Language Runtime no confirma la pila de subprocesos completa inmediatamente cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-130">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10ad8-131">Los hosts no administrados pueden usar la marca de inicio `STARTUP_DISABLE_COMMITTHREADSTACK` en la enumeración [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="10ad8-131">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ad8-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10ad8-132">Example</span></span>  

 <span data-ttu-id="10ad8-133">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="10ad8-133">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10ad8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="10ad8-134">See also</span></span>

- [<span data-ttu-id="10ad8-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="10ad8-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="10ad8-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="10ad8-136">Configuration File Schema</span></span>](../index.md)

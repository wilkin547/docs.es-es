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
ms.openlocfilehash: f717f57fe8670b126ed1468713a2114aaa772762
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198995"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="de3fd-102">\<disableCommitThreadStack> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="de3fd-102">\<disableCommitThreadStack> Element</span></span>

<span data-ttu-id="de3fd-103">Especifica si se confirma la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="de3fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de3fd-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de3fd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de3fd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="de3fd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="de3fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de3fd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="de3fd-107">Attributes</span></span>  
  
|<span data-ttu-id="de3fd-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="de3fd-108">Attribute</span></span>|<span data-ttu-id="de3fd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="de3fd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de3fd-110">enabled</span><span class="sxs-lookup"><span data-stu-id="de3fd-110">enabled</span></span>|<span data-ttu-id="de3fd-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="de3fd-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="de3fd-112">Especifica si la confirmación de la pila de subprocesos completa cuando se inicia el subproceso (comportamiento predeterminado) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="de3fd-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="de3fd-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="de3fd-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="de3fd-114">Value</span><span class="sxs-lookup"><span data-stu-id="de3fd-114">Value</span></span>|<span data-ttu-id="de3fd-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="de3fd-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de3fd-116">0</span><span class="sxs-lookup"><span data-stu-id="de3fd-116">0</span></span>|<span data-ttu-id="de3fd-117">No deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="de3fd-118">1</span><span class="sxs-lookup"><span data-stu-id="de3fd-118">1</span></span>|<span data-ttu-id="de3fd-119">Deshabilite el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de3fd-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de3fd-120">Child Elements</span></span>  

 <span data-ttu-id="de3fd-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="de3fd-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de3fd-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de3fd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="de3fd-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="de3fd-123">Element</span></span>|<span data-ttu-id="de3fd-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="de3fd-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="de3fd-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de3fd-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="de3fd-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="de3fd-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de3fd-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de3fd-127">Remarks</span></span>  

 <span data-ttu-id="de3fd-128">El comportamiento predeterminado de Common Language Runtime consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="de3fd-129">Si se debe crear un gran número de subprocesos en un servidor con memoria limitada y la mayoría de estos subprocesos usarán muy poco espacio de pila, el servidor mejorará su rendimiento si Common Language Runtime no confirma la pila de subprocesos completa inmediatamente cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de3fd-130">Los hosts no administrados pueden usar la marca de inicio `STARTUP_DISABLE_COMMITTHREADSTACK` en la enumeración [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="de3fd-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de3fd-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de3fd-131">Example</span></span>  

 <span data-ttu-id="de3fd-132">En el ejemplo siguiente se muestra cómo deshabilitar el comportamiento predeterminado de Common Language Runtime, que consiste en confirmar la pila de subprocesos completa cuando se inicia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de3fd-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de3fd-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de3fd-133">See also</span></span>

- [<span data-ttu-id="de3fd-134">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="de3fd-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="de3fd-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="de3fd-135">Configuration File Schema</span></span>](../index.md)

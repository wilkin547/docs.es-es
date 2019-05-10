---
title: elemento < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754675"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="bdafc-102">\<Crst_DisableSpinWait > elemento</span><span class="sxs-lookup"><span data-stu-id="bdafc-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="bdafc-103">Especifica si se deshabilita el ciclo de espera para una sección crítica cuando contenidos.</span><span class="sxs-lookup"><span data-stu-id="bdafc-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="bdafc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bdafc-104">\<configuration></span></span>  
<span data-ttu-id="bdafc-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="bdafc-105">\<runtime></span></span>  
<span data-ttu-id="bdafc-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="bdafc-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdafc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdafc-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdafc-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdafc-108">Attributes and Elements</span></span>

<span data-ttu-id="bdafc-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdafc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdafc-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdafc-110">Attributes</span></span>  
  
|<span data-ttu-id="bdafc-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdafc-111">Attribute</span></span>|<span data-ttu-id="bdafc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdafc-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdafc-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="bdafc-113">**enabled**</span></span>|<span data-ttu-id="bdafc-114">Especifica si está deshabilitado el ciclo de espera para las secciones críticas al que están contenidos.</span><span class="sxs-lookup"><span data-stu-id="bdafc-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bdafc-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="bdafc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bdafc-116">Valor</span><span class="sxs-lookup"><span data-stu-id="bdafc-116">Value</span></span>|<span data-ttu-id="bdafc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdafc-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdafc-118">1</span><span class="sxs-lookup"><span data-stu-id="bdafc-118">1</span></span>|<span data-ttu-id="bdafc-119">Deshabilite el ciclo de espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="bdafc-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="bdafc-120">0</span><span class="sxs-lookup"><span data-stu-id="bdafc-120">0</span></span>|<span data-ttu-id="bdafc-121">No deshabilite el ciclo de espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="bdafc-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="bdafc-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bdafc-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdafc-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdafc-123">Child Elements</span></span>  
 <span data-ttu-id="bdafc-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bdafc-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdafc-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdafc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bdafc-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdafc-126">Element</span></span>|<span data-ttu-id="bdafc-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdafc-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdafc-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bdafc-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bdafc-129">Contiene información sobre las diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bdafc-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bdafc-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdafc-130">Example</span></span>  

<span data-ttu-id="bdafc-131">El siguiente ejemplo se deshabilita en espera flechas en las secciones críticas cuando contenidos.</span><span class="sxs-lookup"><span data-stu-id="bdafc-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdafc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdafc-132">See also</span></span>

- [<span data-ttu-id="bdafc-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bdafc-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="bdafc-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bdafc-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

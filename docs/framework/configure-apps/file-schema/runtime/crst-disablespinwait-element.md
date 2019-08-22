---
title: < elemento > Crst_DisableSpinWait
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663838"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="c4765-102">\<Crst_DisableSpinWait >, elemento</span><span class="sxs-lookup"><span data-stu-id="c4765-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="c4765-103">Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="c4765-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="c4765-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c4765-104">\<configuration></span></span>  
<span data-ttu-id="c4765-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c4765-105">\<runtime></span></span>  
<span data-ttu-id="c4765-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="c4765-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4765-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4765-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4765-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4765-108">Attributes and Elements</span></span>

<span data-ttu-id="c4765-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c4765-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4765-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4765-110">Attributes</span></span>  
  
|<span data-ttu-id="c4765-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4765-111">Attribute</span></span>|<span data-ttu-id="c4765-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4765-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4765-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="c4765-113">**enabled**</span></span>|<span data-ttu-id="c4765-114">Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.</span><span class="sxs-lookup"><span data-stu-id="c4765-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c4765-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="c4765-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c4765-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c4765-116">Value</span></span>|<span data-ttu-id="c4765-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4765-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4765-118">1</span><span class="sxs-lookup"><span data-stu-id="c4765-118">1</span></span>|<span data-ttu-id="c4765-119">Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="c4765-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="c4765-120">0</span><span class="sxs-lookup"><span data-stu-id="c4765-120">0</span></span>|<span data-ttu-id="c4765-121">No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="c4765-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="c4765-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c4765-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4765-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4765-123">Child Elements</span></span>  
 <span data-ttu-id="c4765-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c4765-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4765-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4765-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c4765-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4765-126">Element</span></span>|<span data-ttu-id="c4765-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4765-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4765-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4765-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4765-129">Contiene información acerca de diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c4765-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4765-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4765-130">Example</span></span>  

<span data-ttu-id="c4765-131">En el ejemplo siguiente se deshabilita la espera de giro en las secciones críticas cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="c4765-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4765-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4765-132">See also</span></span>

- [<span data-ttu-id="c4765-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c4765-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c4765-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c4765-134">Configuration File Schema</span></span>](../index.md)

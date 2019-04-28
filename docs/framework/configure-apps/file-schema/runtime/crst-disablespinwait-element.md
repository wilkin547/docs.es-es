---
title: elemento < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704835"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="80cb9-102">\<Crst_DisableSpinWait > elemento</span><span class="sxs-lookup"><span data-stu-id="80cb9-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="80cb9-103">Especifica si se deshabilita el ciclo de espera para una sección crítica cuando contenidos.</span><span class="sxs-lookup"><span data-stu-id="80cb9-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span> \ 
  
 <span data-ttu-id="80cb9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="80cb9-104">\<configuration></span></span>  
<span data-ttu-id="80cb9-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="80cb9-105">\<runtime></span></span>  
<span data-ttu-id="80cb9-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="80cb9-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cb9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80cb9-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80cb9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80cb9-108">Attributes and Elements</span></span>

<span data-ttu-id="80cb9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80cb9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80cb9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="80cb9-110">Attributes</span></span>  
  
|<span data-ttu-id="80cb9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="80cb9-111">Attribute</span></span>|<span data-ttu-id="80cb9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cb9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80cb9-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="80cb9-113">**enabled**</span></span>|<span data-ttu-id="80cb9-114">Especifica si el ciclo de espera para las secciones críticas está habilitada cuando están contenidos.</span><span class="sxs-lookup"><span data-stu-id="80cb9-114">Specifies whether spin-waiting for critical sections is enabled when they are contended.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="80cb9-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="80cb9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="80cb9-116">Valor</span><span class="sxs-lookup"><span data-stu-id="80cb9-116">Value</span></span>|<span data-ttu-id="80cb9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cb9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80cb9-118">1</span><span class="sxs-lookup"><span data-stu-id="80cb9-118">1</span></span>|<span data-ttu-id="80cb9-119">Ciclo de espera está habilitado.</span><span class="sxs-lookup"><span data-stu-id="80cb9-119">Spin-waiting is enabled.</span></span>|  
|<span data-ttu-id="80cb9-120">0</span><span class="sxs-lookup"><span data-stu-id="80cb9-120">0</span></span>|<span data-ttu-id="80cb9-121">Ciclo de espera está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="80cb9-121">Spin-waiting is disabled.</span></span> <span data-ttu-id="80cb9-122">Este es el valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="80cb9-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80cb9-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80cb9-123">Child Elements</span></span>  
 <span data-ttu-id="80cb9-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80cb9-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80cb9-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80cb9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="80cb9-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="80cb9-126">Element</span></span>|<span data-ttu-id="80cb9-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cb9-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="80cb9-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80cb9-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="80cb9-129">Contiene información sobre las diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80cb9-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80cb9-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80cb9-130">Example</span></span>  

<span data-ttu-id="80cb9-131">El siguiente ejemplo se deshabilita en espera flechas en las secciones críticas cuando contenidos.</span><span class="sxs-lookup"><span data-stu-id="80cb9-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80cb9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="80cb9-132">See also</span></span>

- [<span data-ttu-id="80cb9-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="80cb9-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="80cb9-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="80cb9-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

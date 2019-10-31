---
title: < elemento > Crst_DisableSpinWait
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117638"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="6a816-102">\<elemento > Crst_DisableSpinWait</span><span class="sxs-lookup"><span data-stu-id="6a816-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="6a816-103">Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="6a816-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="6a816-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a816-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6a816-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a816-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6a816-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="6a816-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a816-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a816-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a816-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6a816-108">Attributes and Elements</span></span>

<span data-ttu-id="6a816-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6a816-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a816-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6a816-110">Attributes</span></span>  
  
|<span data-ttu-id="6a816-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6a816-111">Attribute</span></span>|<span data-ttu-id="6a816-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a816-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a816-113">**activó**</span><span class="sxs-lookup"><span data-stu-id="6a816-113">**enabled**</span></span>|<span data-ttu-id="6a816-114">Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.</span><span class="sxs-lookup"><span data-stu-id="6a816-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6a816-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="6a816-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6a816-116">Valor</span><span class="sxs-lookup"><span data-stu-id="6a816-116">Value</span></span>|<span data-ttu-id="6a816-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a816-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6a816-118">1</span><span class="sxs-lookup"><span data-stu-id="6a816-118">1</span></span>|<span data-ttu-id="6a816-119">Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="6a816-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="6a816-120">0</span><span class="sxs-lookup"><span data-stu-id="6a816-120">0</span></span>|<span data-ttu-id="6a816-121">No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="6a816-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="6a816-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6a816-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a816-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6a816-123">Child Elements</span></span>  
 <span data-ttu-id="6a816-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6a816-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a816-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6a816-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6a816-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a816-126">Element</span></span>|<span data-ttu-id="6a816-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a816-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6a816-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a816-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6a816-129">Contiene información acerca de diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6a816-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6a816-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a816-130">Example</span></span>  

<span data-ttu-id="6a816-131">En el ejemplo siguiente se deshabilita la espera de giro en las secciones críticas cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="6a816-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a816-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a816-132">See also</span></span>

- [<span data-ttu-id="6a816-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6a816-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6a816-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6a816-134">Configuration File Schema</span></span>](../index.md)

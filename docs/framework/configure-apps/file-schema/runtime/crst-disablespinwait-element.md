---
description: 'Más información acerca de: <Crst_DisableSpinWait elemento>'
title: Elemento <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: fca6fed2dabc3d1319ad030bb13bbb35a561b9aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795110"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="a6e02-103">\<Crst_DisableSpinWait> (elemento)</span><span class="sxs-lookup"><span data-stu-id="a6e02-103">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="a6e02-104">Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="a6e02-104">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="a6e02-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6e02-105">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6e02-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6e02-106">Attributes and Elements</span></span>

<span data-ttu-id="a6e02-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6e02-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6e02-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6e02-108">Attributes</span></span>  
  
|<span data-ttu-id="a6e02-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6e02-109">Attribute</span></span>|<span data-ttu-id="a6e02-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6e02-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6e02-111">**enabled**</span><span class="sxs-lookup"><span data-stu-id="a6e02-111">**enabled**</span></span>|<span data-ttu-id="a6e02-112">Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.</span><span class="sxs-lookup"><span data-stu-id="a6e02-112">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a6e02-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a6e02-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="a6e02-114">Value</span><span class="sxs-lookup"><span data-stu-id="a6e02-114">Value</span></span>|<span data-ttu-id="a6e02-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6e02-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6e02-116">1</span><span class="sxs-lookup"><span data-stu-id="a6e02-116">1</span></span>|<span data-ttu-id="a6e02-117">Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="a6e02-117">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="a6e02-118">0</span><span class="sxs-lookup"><span data-stu-id="a6e02-118">0</span></span>|<span data-ttu-id="a6e02-119">No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="a6e02-119">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="a6e02-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a6e02-120">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6e02-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6e02-121">Child Elements</span></span>  

 <span data-ttu-id="a6e02-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6e02-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6e02-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6e02-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a6e02-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6e02-124">Element</span></span>|<span data-ttu-id="a6e02-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6e02-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a6e02-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6e02-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a6e02-127">Contiene información acerca de diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6e02-127">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a6e02-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6e02-128">Example</span></span>  

<span data-ttu-id="a6e02-129">En el ejemplo siguiente se deshabilita la espera de giro en las secciones críticas cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="a6e02-129">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6e02-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6e02-130">See also</span></span>

- [<span data-ttu-id="a6e02-131">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a6e02-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a6e02-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a6e02-132">Configuration File Schema</span></span>](../index.md)

---
title: Elemento <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151355"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="8325f-102">\<Crst_DisableSpinWait> (elemento)</span><span class="sxs-lookup"><span data-stu-id="8325f-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="8325f-103">Especifica si se va a deshabilitar la espera de giro para una sección crítica cuando esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="8325f-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="8325f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8325f-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8325f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8325f-105">Attributes and Elements</span></span>

<span data-ttu-id="8325f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8325f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8325f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8325f-107">Attributes</span></span>  
  
|<span data-ttu-id="8325f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8325f-108">Attribute</span></span>|<span data-ttu-id="8325f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8325f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8325f-110">**enabled**</span><span class="sxs-lookup"><span data-stu-id="8325f-110">**enabled**</span></span>|<span data-ttu-id="8325f-111">Especifica si está deshabilitada la espera de girar para las secciones críticas cuando están configuradas.</span><span class="sxs-lookup"><span data-stu-id="8325f-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8325f-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="8325f-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="8325f-113">Valor</span><span class="sxs-lookup"><span data-stu-id="8325f-113">Value</span></span>|<span data-ttu-id="8325f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8325f-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8325f-115">1</span><span class="sxs-lookup"><span data-stu-id="8325f-115">1</span></span>|<span data-ttu-id="8325f-116">Deshabilitar el giro en espera cuando no se puede adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="8325f-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="8325f-117">0</span><span class="sxs-lookup"><span data-stu-id="8325f-117">0</span></span>|<span data-ttu-id="8325f-118">No deshabilite la espera de giro cuando no se pueda adquirir una sección crítica.</span><span class="sxs-lookup"><span data-stu-id="8325f-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="8325f-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8325f-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8325f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8325f-120">Child Elements</span></span>  

 <span data-ttu-id="8325f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8325f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8325f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8325f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8325f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8325f-123">Element</span></span>|<span data-ttu-id="8325f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="8325f-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8325f-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8325f-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8325f-126">Contiene información acerca de diversas opciones de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8325f-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8325f-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8325f-127">Example</span></span>  

<span data-ttu-id="8325f-128">En el ejemplo siguiente se deshabilita la espera de giro en las secciones críticas cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="8325f-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8325f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8325f-129">See also</span></span>

- [<span data-ttu-id="8325f-130">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8325f-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8325f-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8325f-131">Configuration File Schema</span></span>](../index.md)

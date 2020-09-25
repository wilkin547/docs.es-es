---
title: <developmentMode> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205027"
---
# <a name="developmentmode-element"></a><span data-ttu-id="83d6a-102">\<developmentMode> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="83d6a-102">\<developmentMode> Element</span></span>

<span data-ttu-id="83d6a-103">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="83d6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83d6a-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83d6a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83d6a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="83d6a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83d6a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83d6a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="83d6a-107">Attributes</span></span>  
  
|<span data-ttu-id="83d6a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="83d6a-108">Attribute</span></span>|<span data-ttu-id="83d6a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="83d6a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83d6a-110">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="83d6a-110">**developerInstallation**</span></span>|<span data-ttu-id="83d6a-111">Especifica si el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="83d6a-112">Atributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="83d6a-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="83d6a-113">Value</span><span class="sxs-lookup"><span data-stu-id="83d6a-113">Value</span></span>|<span data-ttu-id="83d6a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="83d6a-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83d6a-115">**true**</span><span class="sxs-lookup"><span data-stu-id="83d6a-115">**true**</span></span>|<span data-ttu-id="83d6a-116">Busca los ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="83d6a-117">**false**</span><span class="sxs-lookup"><span data-stu-id="83d6a-117">**false**</span></span>|<span data-ttu-id="83d6a-118">No busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="83d6a-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83d6a-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83d6a-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83d6a-120">Child Elements</span></span>  

 <span data-ttu-id="83d6a-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83d6a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83d6a-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83d6a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="83d6a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="83d6a-123">Element</span></span>|<span data-ttu-id="83d6a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="83d6a-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83d6a-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83d6a-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="83d6a-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="83d6a-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83d6a-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83d6a-127">Remarks</span></span>  

 <span data-ttu-id="83d6a-128">Use esta configuración solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="83d6a-128">Use this setting only at development time.</span></span> <span data-ttu-id="83d6a-129">El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="83d6a-130">Simplemente usa el primer ensamblado que encuentra.</span><span class="sxs-lookup"><span data-stu-id="83d6a-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83d6a-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83d6a-131">Example</span></span>  

 <span data-ttu-id="83d6a-132">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="83d6a-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83d6a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83d6a-133">See also</span></span>

- [<span data-ttu-id="83d6a-134">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="83d6a-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83d6a-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="83d6a-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="83d6a-136">Procedimiento para buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="83d6a-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)

---
title: <probing> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
ms.openlocfilehash: e9e48ea97e1b70fef7fcc78a113e18c5fec23b7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115863"
---
# <a name="probing-element"></a><span data-ttu-id="efba5-102">\<probing> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="efba5-102">\<probing> Element</span></span>
<span data-ttu-id="efba5-103">Especifica los subdirectorios base de la aplicación para los Common Language Runtime que se van a buscar al cargar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="efba5-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="efba5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efba5-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efba5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="efba5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="efba5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="efba5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efba5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="efba5-107">Attributes</span></span>  
  
|<span data-ttu-id="efba5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="efba5-108">Attribute</span></span>|<span data-ttu-id="efba5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="efba5-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="efba5-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="efba5-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="efba5-111">Especifica los subdirectorios del directorio base de la aplicación que pueden contener ensamblados.</span><span class="sxs-lookup"><span data-stu-id="efba5-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="efba5-112">Delimita cada subdirectorio con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="efba5-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efba5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="efba5-113">Child Elements</span></span>  

<span data-ttu-id="efba5-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="efba5-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efba5-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="efba5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="efba5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="efba5-116">Element</span></span>|<span data-ttu-id="efba5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="efba5-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="efba5-118">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="efba5-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="efba5-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="efba5-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="efba5-120">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="efba5-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="efba5-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efba5-121">Example</span></span>  
 <span data-ttu-id="efba5-122">En el ejemplo siguiente se muestra cómo especificar subdirectorios base de la aplicación en el que el tiempo de ejecución debe buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="efba5-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="efba5-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efba5-123">See also</span></span>

- [<span data-ttu-id="efba5-124">Esquema de configuración en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="efba5-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="efba5-125">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="efba5-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="efba5-126">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="efba5-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="efba5-127">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="efba5-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

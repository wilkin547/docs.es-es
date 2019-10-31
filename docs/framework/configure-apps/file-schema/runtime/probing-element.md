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
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115863"
---
# <a name="probing-element"></a><span data-ttu-id="df77e-102">\<el elemento > de sondeo</span><span class="sxs-lookup"><span data-stu-id="df77e-102">\<probing> Element</span></span>
<span data-ttu-id="df77e-103">Especifica los subdirectorios base de la aplicación para los Common Language Runtime que se van a buscar al cargar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="df77e-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="df77e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="df77e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="df77e-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="df77e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="df77e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="df77e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="df77e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**sondeo**\<</span><span class="sxs-lookup"><span data-stu-id="df77e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df77e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df77e-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df77e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="df77e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df77e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="df77e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df77e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="df77e-111">Attributes</span></span>  
  
|<span data-ttu-id="df77e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="df77e-112">Attribute</span></span>|<span data-ttu-id="df77e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="df77e-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="df77e-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="df77e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="df77e-115">Especifica los subdirectorios del directorio base de la aplicación que pueden contener ensamblados.</span><span class="sxs-lookup"><span data-stu-id="df77e-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="df77e-116">Delimita cada subdirectorio con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="df77e-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df77e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="df77e-117">Child Elements</span></span>  

<span data-ttu-id="df77e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="df77e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df77e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="df77e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="df77e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="df77e-120">Element</span></span>|<span data-ttu-id="df77e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="df77e-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="df77e-122">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="df77e-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="df77e-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df77e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="df77e-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="df77e-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="df77e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df77e-125">Example</span></span>  
 <span data-ttu-id="df77e-126">En el ejemplo siguiente se muestra cómo especificar subdirectorios base de la aplicación en el que el tiempo de ejecución debe buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="df77e-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df77e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="df77e-127">See also</span></span>

- [<span data-ttu-id="df77e-128">Esquema de configuración en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="df77e-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="df77e-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="df77e-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="df77e-130">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="df77e-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="df77e-131">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="df77e-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

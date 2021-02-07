---
description: 'Más información acerca de: <probing> elemento'
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
ms.openlocfilehash: 404e53f735ce02c2a3d7911216f834d38e309789
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726109"
---
# <a name="probing-element"></a><span data-ttu-id="b231f-103">\<probing> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="b231f-103">\<probing> Element</span></span>

<span data-ttu-id="b231f-104">Especifica los subdirectorios base de la aplicación para los Common Language Runtime que se van a buscar al cargar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b231f-104">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="b231f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b231f-105">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b231f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b231f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b231f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b231f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b231f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b231f-108">Attributes</span></span>  
  
|<span data-ttu-id="b231f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="b231f-109">Attribute</span></span>|<span data-ttu-id="b231f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b231f-110">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="b231f-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b231f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="b231f-112">Especifica los subdirectorios del directorio base de la aplicación que pueden contener ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b231f-112">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="b231f-113">Delimita cada subdirectorio con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="b231f-113">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b231f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b231f-114">Child Elements</span></span>  

<span data-ttu-id="b231f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b231f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b231f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b231f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b231f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b231f-117">Element</span></span>|<span data-ttu-id="b231f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b231f-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="b231f-119">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b231f-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="b231f-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b231f-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b231f-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b231f-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b231f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b231f-122">Example</span></span>  

 <span data-ttu-id="b231f-123">En el ejemplo siguiente se muestra cómo especificar subdirectorios base de la aplicación en el que el tiempo de ejecución debe buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b231f-123">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b231f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b231f-124">See also</span></span>

- [<span data-ttu-id="b231f-125">Esquema de configuración en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b231f-125">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="b231f-126">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b231f-126">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="b231f-127">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="b231f-127">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="b231f-128">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="b231f-128">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

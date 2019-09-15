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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae789e99a1306102c67f2252760e215989132406
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971624"
---
# <a name="probing-element"></a><span data-ttu-id="5cb7e-102">\<sondeo de > elemento</span><span class="sxs-lookup"><span data-stu-id="5cb7e-102">\<probing> Element</span></span>
<span data-ttu-id="5cb7e-103">Especifica los subdirectorios base de la aplicación para los Common Language Runtime que se van a buscar al cargar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="5cb7e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cb7e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5cb7e-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cb7e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5cb7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="5cb7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="5cb7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<probing>**</span><span class="sxs-lookup"><span data-stu-id="5cb7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb7e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cb7e-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cb7e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5cb7e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5cb7e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cb7e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5cb7e-111">Attributes</span></span>  
  
|<span data-ttu-id="5cb7e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cb7e-112">Attribute</span></span>|<span data-ttu-id="5cb7e-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb7e-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="5cb7e-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5cb7e-115">Especifica los subdirectorios del directorio base de la aplicación que pueden contener ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="5cb7e-116">Delimita cada subdirectorio con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cb7e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5cb7e-117">Child Elements</span></span>  

<span data-ttu-id="5cb7e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cb7e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5cb7e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5cb7e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cb7e-120">Element</span></span>|<span data-ttu-id="5cb7e-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb7e-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="5cb7e-122">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="5cb7e-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5cb7e-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5cb7e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cb7e-125">Example</span></span>  
 <span data-ttu-id="5cb7e-126">En el ejemplo siguiente se muestra cómo especificar subdirectorios base de la aplicación en el que el tiempo de ejecución debe buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5cb7e-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cb7e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb7e-127">See also</span></span>

- [<span data-ttu-id="5cb7e-128">Esquema de configuración en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5cb7e-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="5cb7e-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5cb7e-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="5cb7e-130">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="5cb7e-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="5cb7e-131">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="5cb7e-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

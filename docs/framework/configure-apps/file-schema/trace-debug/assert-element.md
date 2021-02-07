---
description: 'Más información acerca de: <assert> elemento'
title: <assert> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: ce8000b30569d0e5ce47a77fbccd4bec833bb5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725992"
---
# <a name="assert-element"></a><span data-ttu-id="1aa0e-103">\<assert> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="1aa0e-103">\<assert> Element</span></span>

<span data-ttu-id="1aa0e-104">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-104">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="1aa0e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1aa0e-105">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aa0e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1aa0e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1aa0e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aa0e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1aa0e-108">Attributes</span></span>  
  
|<span data-ttu-id="1aa0e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1aa0e-109">Attribute</span></span>|<span data-ttu-id="1aa0e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aa0e-110">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="1aa0e-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1aa0e-112">Especifica si se va a mostrar un cuadro de mensaje cuando el método **Debug. Assert** se evalúe como **false**.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-112">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="1aa0e-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1aa0e-114">Especifica el nombre del archivo en el que se va a escribir el mensaje si **Debug. Assert** se evalúa como **false**.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-114">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="1aa0e-115">Atributo assertuienabled</span><span class="sxs-lookup"><span data-stu-id="1aa0e-115">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="1aa0e-116">Value</span><span class="sxs-lookup"><span data-stu-id="1aa0e-116">Value</span></span>|<span data-ttu-id="1aa0e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aa0e-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="1aa0e-118">Muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-118">Displays the message box.</span></span> <span data-ttu-id="1aa0e-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-119">This is the default.</span></span>|  
|`false`|<span data-ttu-id="1aa0e-120">No muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-120">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aa0e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1aa0e-121">Child Elements</span></span>  

 <span data-ttu-id="1aa0e-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1aa0e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1aa0e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1aa0e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1aa0e-124">Element</span></span>|<span data-ttu-id="1aa0e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aa0e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1aa0e-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1aa0e-127">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-127">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa0e-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1aa0e-128">Remarks</span></span>  

 <span data-ttu-id="1aa0e-129">Ambos atributos del **\<assert>** elemento son opcionales.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-129">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="1aa0e-130">Puede deshabilitar los cuadros de mensaje sin especificar un archivo en el que escribir los mensajes, o puede especificar un archivo en el que escribir los mensajes mientras se deshabilitan los cuadros de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1aa0e-130">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa0e-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1aa0e-131">Example</span></span>  

 <span data-ttu-id="1aa0e-132">En el ejemplo siguiente se muestra cómo deshabilitar la visualización de cuadros de mensaje cuando se llama a **Debug. Assert** y se escriben los mensajes en `c:\log.txt` .</span><span class="sxs-lookup"><span data-stu-id="1aa0e-132">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1aa0e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aa0e-133">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="1aa0e-134">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="1aa0e-134">Trace and Debug Settings Schema</span></span>](index.md)

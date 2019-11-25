---
title: <assert> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088948"
---
# <a name="assert-element"></a><span data-ttu-id="47d36-102">\<elemento > Assert</span><span class="sxs-lookup"><span data-stu-id="47d36-102">\<assert> Element</span></span>
<span data-ttu-id="47d36-103">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="47d36-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

<span data-ttu-id="47d36-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47d36-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47d36-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="47d36-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="47d36-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Assert >**</span><span class="sxs-lookup"><span data-stu-id="47d36-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>

## <a name="syntax"></a><span data-ttu-id="47d36-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47d36-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47d36-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47d36-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47d36-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47d36-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47d36-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="47d36-110">Attributes</span></span>  
  
|<span data-ttu-id="47d36-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="47d36-111">Attribute</span></span>|<span data-ttu-id="47d36-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="47d36-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="47d36-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="47d36-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="47d36-114">Especifica si se va a mostrar un cuadro de mensaje cuando el método **Debug. Assert** se evalúe como **false**.</span><span class="sxs-lookup"><span data-stu-id="47d36-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="47d36-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="47d36-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="47d36-116">Especifica el nombre del archivo en el que se va a escribir el mensaje si **Debug. Assert** se evalúa como **false**.</span><span class="sxs-lookup"><span data-stu-id="47d36-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="47d36-117">Atributo assertuienabled</span><span class="sxs-lookup"><span data-stu-id="47d36-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="47d36-118">Valor</span><span class="sxs-lookup"><span data-stu-id="47d36-118">Value</span></span>|<span data-ttu-id="47d36-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="47d36-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="47d36-120">Muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="47d36-120">Displays the message box.</span></span> <span data-ttu-id="47d36-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="47d36-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="47d36-122">No muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="47d36-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47d36-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47d36-123">Child Elements</span></span>  
 <span data-ttu-id="47d36-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47d36-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47d36-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47d36-125">Parent Elements</span></span>  
  
|<span data-ttu-id="47d36-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="47d36-126">Element</span></span>|<span data-ttu-id="47d36-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="47d36-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="47d36-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47d36-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="47d36-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="47d36-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47d36-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47d36-130">Remarks</span></span>  
 <span data-ttu-id="47d36-131">Ambos atributos del elemento **\<Assert >** son opcionales.</span><span class="sxs-lookup"><span data-stu-id="47d36-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="47d36-132">Puede deshabilitar los cuadros de mensaje sin especificar un archivo en el que escribir los mensajes, o puede especificar un archivo en el que escribir los mensajes mientras se deshabilitan los cuadros de mensaje.</span><span class="sxs-lookup"><span data-stu-id="47d36-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d36-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47d36-133">Example</span></span>  
 <span data-ttu-id="47d36-134">En el ejemplo siguiente se muestra cómo deshabilitar la visualización de cuadros de mensaje cuando se llama a **Debug. Assert** y se escriben los mensajes en `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="47d36-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47d36-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="47d36-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="47d36-136">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="47d36-136">Trace and Debug Settings Schema</span></span>](index.md)

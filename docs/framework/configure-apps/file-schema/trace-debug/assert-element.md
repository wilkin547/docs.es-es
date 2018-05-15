---
title: '&lt;Assert&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ab1644d23e4d6d78b62e701902e5ec39e134b38b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltassertgt-element"></a><span data-ttu-id="2c892-102">&lt;Assert&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="2c892-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="2c892-103">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2c892-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="2c892-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c892-104">\<configuration></span></span>  
<span data-ttu-id="2c892-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="2c892-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2c892-106">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="2c892-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c892-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c892-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c892-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2c892-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c892-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2c892-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c892-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c892-110">Attributes</span></span>  
  
|<span data-ttu-id="2c892-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2c892-111">Attribute</span></span>|<span data-ttu-id="2c892-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c892-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="2c892-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2c892-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2c892-114">Especifica si mostrar un cuadro de mensaje cuando el **Debug.Assert** se evalúa como método **false**.</span><span class="sxs-lookup"><span data-stu-id="2c892-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="2c892-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2c892-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2c892-116">Especifica el nombre del archivo que se escribirá el mensaje como si **Debug.Assert** se evalúa como **false**.</span><span class="sxs-lookup"><span data-stu-id="2c892-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="2c892-117">Atributo AssertUiEnabled</span><span class="sxs-lookup"><span data-stu-id="2c892-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="2c892-118">Valor</span><span class="sxs-lookup"><span data-stu-id="2c892-118">Value</span></span>|<span data-ttu-id="2c892-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c892-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2c892-120">Muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c892-120">Displays the message box.</span></span> <span data-ttu-id="2c892-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2c892-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="2c892-122">No muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c892-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c892-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2c892-123">Child Elements</span></span>  
 <span data-ttu-id="2c892-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2c892-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c892-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2c892-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2c892-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c892-126">Element</span></span>|<span data-ttu-id="2c892-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c892-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c892-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c892-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2c892-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2c892-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c892-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c892-130">Remarks</span></span>  
 <span data-ttu-id="2c892-131">Ambos atributos en el  **\<assert >** elemento son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2c892-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="2c892-132">Puede deshabilitar los cuadros de mensaje sin especificar un archivo para escribir los mensajes en, o puede especificar un archivo para escribir mensajes mientras se realiza la dejando mensaje cuadros habilitados.</span><span class="sxs-lookup"><span data-stu-id="2c892-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c892-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c892-133">Example</span></span>  
 <span data-ttu-id="2c892-134">En el ejemplo siguiente se muestra cómo deshabilitar la presentación de los cuadros de mensaje cuando se llama a **Debug.Assert** y escribir los mensajes a `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="2c892-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c892-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c892-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="2c892-136">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="2c892-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

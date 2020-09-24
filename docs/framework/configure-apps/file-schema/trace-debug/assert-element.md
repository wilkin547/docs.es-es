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
ms.openlocfilehash: eb29701912a45a484b1716195b449e8a97d1d4b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149301"
---
# <a name="assert-element"></a><span data-ttu-id="ebee3-102">\<assert> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="ebee3-102">\<assert> Element</span></span>

<span data-ttu-id="ebee3-103">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ebee3-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="ebee3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebee3-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebee3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ebee3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ebee3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ebee3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebee3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ebee3-107">Attributes</span></span>  
  
|<span data-ttu-id="ebee3-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ebee3-108">Attribute</span></span>|<span data-ttu-id="ebee3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebee3-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="ebee3-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebee3-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ebee3-111">Especifica si se va a mostrar un cuadro de mensaje cuando el método **Debug. Assert** se evalúe como **false**.</span><span class="sxs-lookup"><span data-stu-id="ebee3-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="ebee3-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebee3-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ebee3-113">Especifica el nombre del archivo en el que se va a escribir el mensaje si **Debug. Assert** se evalúa como **false**.</span><span class="sxs-lookup"><span data-stu-id="ebee3-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="ebee3-114">Atributo assertuienabled</span><span class="sxs-lookup"><span data-stu-id="ebee3-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="ebee3-115">Valor</span><span class="sxs-lookup"><span data-stu-id="ebee3-115">Value</span></span>|<span data-ttu-id="ebee3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebee3-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="ebee3-117">Muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ebee3-117">Displays the message box.</span></span> <span data-ttu-id="ebee3-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ebee3-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="ebee3-119">No muestra el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ebee3-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebee3-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ebee3-120">Child Elements</span></span>  

 <span data-ttu-id="ebee3-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ebee3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebee3-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ebee3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ebee3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebee3-123">Element</span></span>|<span data-ttu-id="ebee3-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebee3-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ebee3-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebee3-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ebee3-126">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebee3-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebee3-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebee3-127">Remarks</span></span>  

 <span data-ttu-id="ebee3-128">Ambos atributos del **\<assert>** elemento son opcionales.</span><span class="sxs-lookup"><span data-stu-id="ebee3-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="ebee3-129">Puede deshabilitar los cuadros de mensaje sin especificar un archivo en el que escribir los mensajes, o puede especificar un archivo en el que escribir los mensajes mientras se deshabilitan los cuadros de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ebee3-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebee3-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebee3-130">Example</span></span>  

 <span data-ttu-id="ebee3-131">En el ejemplo siguiente se muestra cómo deshabilitar la visualización de cuadros de mensaje cuando se llama a **Debug. Assert** y se escriben los mensajes en `c:\log.txt` .</span><span class="sxs-lookup"><span data-stu-id="ebee3-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebee3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebee3-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="ebee3-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="ebee3-133">Trace and Debug Settings Schema</span></span>](index.md)

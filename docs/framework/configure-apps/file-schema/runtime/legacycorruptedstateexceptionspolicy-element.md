---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116455"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="0944e-102">\<elemento > legacyCorruptedStateExceptionsPolicy</span><span class="sxs-lookup"><span data-stu-id="0944e-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="0944e-103">Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.</span><span class="sxs-lookup"><span data-stu-id="0944e-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
<span data-ttu-id="0944e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0944e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0944e-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0944e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0944e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyCorruptedStateExceptionsPolicy >**</span><span class="sxs-lookup"><span data-stu-id="0944e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0944e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0944e-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0944e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0944e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0944e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0944e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0944e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0944e-110">Attributes</span></span>  
  
|<span data-ttu-id="0944e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0944e-111">Attribute</span></span>|<span data-ttu-id="0944e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0944e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0944e-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0944e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0944e-114">Especifica que la aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="0944e-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0944e-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="0944e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0944e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="0944e-116">Value</span></span>|<span data-ttu-id="0944e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0944e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0944e-118">La aplicación no detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="0944e-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="0944e-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0944e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0944e-120">La aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="0944e-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0944e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0944e-121">Child Elements</span></span>  
 <span data-ttu-id="0944e-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0944e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0944e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0944e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0944e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0944e-124">Element</span></span>|<span data-ttu-id="0944e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0944e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0944e-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0944e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0944e-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0944e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0944e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0944e-128">Remarks</span></span>  
 <span data-ttu-id="0944e-129">En la .NET Framework versión 3,5 y versiones anteriores, el Common Language Runtime permitía que el código administrado detectara las excepciones que se producían con Estados de proceso dañados.</span><span class="sxs-lookup"><span data-stu-id="0944e-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="0944e-130">Una infracción de acceso es un ejemplo de este tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="0944e-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="0944e-131">A partir de la .NET Framework 4, el código administrado ya no detecta estos tipos de excepciones en `catch` bloques.</span><span class="sxs-lookup"><span data-stu-id="0944e-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="0944e-132">Sin embargo, puede invalidar este cambio y mantener el control de las excepciones de estado dañadas de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="0944e-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="0944e-133">Establezca el atributo `enabled` del elemento de `<legacyCorruptedStateExceptionsPolicy>` en `true`.</span><span class="sxs-lookup"><span data-stu-id="0944e-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="0944e-134">Esta opción de configuración se aplica processwide y afecta a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="0944e-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="0944e-135">o bien</span><span class="sxs-lookup"><span data-stu-id="0944e-135">-or-</span></span>  
  
- <span data-ttu-id="0944e-136">Aplique el atributo <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al método que contiene las excepciones `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="0944e-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="0944e-137">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0944e-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0944e-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0944e-138">Example</span></span>  
 <span data-ttu-id="0944e-139">En el ejemplo siguiente se muestra cómo especificar que la aplicación debe volver al comportamiento anterior a la .NET Framework 4 y detectar todos los errores de excepción de estado dañado.</span><span class="sxs-lookup"><span data-stu-id="0944e-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0944e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0944e-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="0944e-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0944e-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0944e-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0944e-142">Configuration File Schema</span></span>](../index.md)

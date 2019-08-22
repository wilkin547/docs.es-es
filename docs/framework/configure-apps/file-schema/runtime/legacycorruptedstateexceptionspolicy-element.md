---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2715548a40579375cebbdd5fb9003738a42ff714
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663651"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="48b00-102">\<legacyCorruptedStateExceptionsPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="48b00-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="48b00-103">Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.</span><span class="sxs-lookup"><span data-stu-id="48b00-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="48b00-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48b00-104">\<configuration></span></span>  
<span data-ttu-id="48b00-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="48b00-105">\<runtime></span></span>  
<span data-ttu-id="48b00-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="48b00-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b00-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48b00-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48b00-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48b00-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48b00-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48b00-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48b00-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="48b00-110">Attributes</span></span>  
  
|<span data-ttu-id="48b00-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="48b00-111">Attribute</span></span>|<span data-ttu-id="48b00-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="48b00-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="48b00-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="48b00-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="48b00-114">Especifica que la aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="48b00-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="48b00-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="48b00-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="48b00-116">Valor</span><span class="sxs-lookup"><span data-stu-id="48b00-116">Value</span></span>|<span data-ttu-id="48b00-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="48b00-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="48b00-118">La aplicación no detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="48b00-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="48b00-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="48b00-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="48b00-120">La aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="48b00-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48b00-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48b00-121">Child Elements</span></span>  
 <span data-ttu-id="48b00-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48b00-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48b00-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48b00-123">Parent Elements</span></span>  
  
|<span data-ttu-id="48b00-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="48b00-124">Element</span></span>|<span data-ttu-id="48b00-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="48b00-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48b00-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48b00-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="48b00-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="48b00-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48b00-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48b00-128">Remarks</span></span>  
 <span data-ttu-id="48b00-129">En la .NET Framework versión 3,5 y versiones anteriores, el Common Language Runtime permitía que el código administrado detectara las excepciones que se producían con Estados de proceso dañados.</span><span class="sxs-lookup"><span data-stu-id="48b00-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="48b00-130">Una infracción de acceso es un ejemplo de este tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="48b00-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="48b00-131">A partir de la .NET Framework 4, el código administrado ya no detecta estos tipos de excepciones `catch` en bloques.</span><span class="sxs-lookup"><span data-stu-id="48b00-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="48b00-132">Sin embargo, puede invalidar este cambio y mantener el control de las excepciones de estado dañadas de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="48b00-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="48b00-133">Establezca el `<legacyCorruptedStateExceptionsPolicy>` atributo del `enabled` elemento en `true`.</span><span class="sxs-lookup"><span data-stu-id="48b00-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="48b00-134">Esta opción de configuración se aplica processwide y afecta a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="48b00-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="48b00-135">-o bien-</span><span class="sxs-lookup"><span data-stu-id="48b00-135">-or-</span></span>  
  
- <span data-ttu-id="48b00-136">Aplique el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atributo al método que contiene el bloque de `catch` excepciones.</span><span class="sxs-lookup"><span data-stu-id="48b00-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="48b00-137">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="48b00-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48b00-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48b00-138">Example</span></span>  
 <span data-ttu-id="48b00-139">En el ejemplo siguiente se muestra cómo especificar que la aplicación debe volver al comportamiento anterior a la .NET Framework 4 y detectar todos los errores de excepción de estado dañado.</span><span class="sxs-lookup"><span data-stu-id="48b00-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48b00-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="48b00-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="48b00-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="48b00-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="48b00-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="48b00-142">Configuration File Schema</span></span>](../index.md)

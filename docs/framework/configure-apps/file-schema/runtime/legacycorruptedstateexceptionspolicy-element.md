---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116455"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="9425f-102">\<legacyCorruptedStateExceptionsPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9425f-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="9425f-103">Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.</span><span class="sxs-lookup"><span data-stu-id="9425f-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="9425f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9425f-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9425f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9425f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9425f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9425f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9425f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9425f-107">Attributes</span></span>  
  
|<span data-ttu-id="9425f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="9425f-108">Attribute</span></span>|<span data-ttu-id="9425f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9425f-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9425f-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9425f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9425f-111">Especifica que la aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="9425f-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9425f-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="9425f-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="9425f-113">Value</span><span class="sxs-lookup"><span data-stu-id="9425f-113">Value</span></span>|<span data-ttu-id="9425f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9425f-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9425f-115">La aplicación no detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="9425f-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="9425f-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9425f-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9425f-117">La aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="9425f-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9425f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9425f-118">Child Elements</span></span>  
 <span data-ttu-id="9425f-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9425f-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9425f-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9425f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9425f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9425f-121">Element</span></span>|<span data-ttu-id="9425f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9425f-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9425f-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9425f-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9425f-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9425f-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9425f-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9425f-125">Remarks</span></span>  
 <span data-ttu-id="9425f-126">En la .NET Framework versión 3,5 y versiones anteriores, el Common Language Runtime permitía que el código administrado detectara las excepciones que se producían con Estados de proceso dañados.</span><span class="sxs-lookup"><span data-stu-id="9425f-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="9425f-127">Una infracción de acceso es un ejemplo de este tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="9425f-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="9425f-128">A partir de la .NET Framework 4, el código administrado ya no detecta estos tipos de excepciones en `catch` bloques.</span><span class="sxs-lookup"><span data-stu-id="9425f-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="9425f-129">Sin embargo, puede invalidar este cambio y mantener el control de las excepciones de estado dañadas de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="9425f-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="9425f-130">Establezca el `<legacyCorruptedStateExceptionsPolicy>` atributo del elemento `enabled` en `true` .</span><span class="sxs-lookup"><span data-stu-id="9425f-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="9425f-131">Esta opción de configuración se aplica processwide y afecta a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="9425f-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="9425f-132">O bien</span><span class="sxs-lookup"><span data-stu-id="9425f-132">-or-</span></span>  
  
- <span data-ttu-id="9425f-133">Aplique el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atributo al método que contiene el bloque de excepciones `catch` .</span><span class="sxs-lookup"><span data-stu-id="9425f-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="9425f-134">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9425f-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9425f-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9425f-135">Example</span></span>  
 <span data-ttu-id="9425f-136">En el ejemplo siguiente se muestra cómo especificar que la aplicación debe volver al comportamiento anterior a la .NET Framework 4 y detectar todos los errores de excepción de estado dañado.</span><span class="sxs-lookup"><span data-stu-id="9425f-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9425f-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9425f-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="9425f-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="9425f-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9425f-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9425f-139">Configuration File Schema</span></span>](../index.md)

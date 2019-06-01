---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8733e11aba30ebea30fc71a5350f76dfd041eb4
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456408"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="1aec2-102">\<legacyCorruptedStateExceptionsPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="1aec2-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="1aec2-103">Especifica si common language runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.</span><span class="sxs-lookup"><span data-stu-id="1aec2-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="1aec2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1aec2-104">\<configuration></span></span>  
<span data-ttu-id="1aec2-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1aec2-105">\<runtime></span></span>  
<span data-ttu-id="1aec2-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="1aec2-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aec2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1aec2-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aec2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1aec2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1aec2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1aec2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aec2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1aec2-110">Attributes</span></span>  
  
|<span data-ttu-id="1aec2-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1aec2-111">Attribute</span></span>|<span data-ttu-id="1aec2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aec2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1aec2-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1aec2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1aec2-114">Especifica que la aplicación detectará si se dañan los errores de excepción de estado como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="1aec2-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1aec2-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="1aec2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1aec2-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1aec2-116">Value</span></span>|<span data-ttu-id="1aec2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aec2-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1aec2-118">La aplicación no detectará si se dañan los errores de excepción de estado como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="1aec2-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="1aec2-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1aec2-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1aec2-120">La aplicación detectará si se dañan los errores de excepción de estado como infracciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="1aec2-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aec2-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1aec2-121">Child Elements</span></span>  
 <span data-ttu-id="1aec2-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1aec2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1aec2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1aec2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1aec2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1aec2-124">Element</span></span>|<span data-ttu-id="1aec2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aec2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1aec2-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1aec2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1aec2-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1aec2-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aec2-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1aec2-128">Remarks</span></span>  
 <span data-ttu-id="1aec2-129">En la versión 3.5 y versiones anterior de .NET Framework, common language runtime permite código administrado detectar excepciones que se han producido por Estados de proceso dañado.</span><span class="sxs-lookup"><span data-stu-id="1aec2-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="1aec2-130">Una infracción de acceso es un ejemplo de este tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="1aec2-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="1aec2-131">A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]administrado código ya no detecta estos tipos de excepciones en `catch` bloques.</span><span class="sxs-lookup"><span data-stu-id="1aec2-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="1aec2-132">Sin embargo, puede invalidar este cambio y mantener el control de excepciones de estado dañado de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="1aec2-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="1aec2-133">Establecer el `<legacyCorruptedStateExceptionsPolicy>` del elemento `enabled` atributo `true`.</span><span class="sxs-lookup"><span data-stu-id="1aec2-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="1aec2-134">Esta opción de configuración está aplicado a todo el proceso y afecta a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="1aec2-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="1aec2-135">-o bien-</span><span class="sxs-lookup"><span data-stu-id="1aec2-135">-or-</span></span>  
  
- <span data-ttu-id="1aec2-136">Aplicar el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al método que contiene las excepciones `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="1aec2-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="1aec2-137">Este elemento de configuración está disponible solo en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1aec2-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aec2-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1aec2-138">Example</span></span>  
 <span data-ttu-id="1aec2-139">El ejemplo siguiente muestra cómo especificar que la aplicación debe revertir al comportamiento antes de .NET Framework 4 y detectar dañen todos los errores de excepción de estado.</span><span class="sxs-lookup"><span data-stu-id="1aec2-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1aec2-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aec2-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="1aec2-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1aec2-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1aec2-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1aec2-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

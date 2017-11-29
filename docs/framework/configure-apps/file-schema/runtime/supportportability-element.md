---
title: '&lt;supportPortability&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b46d12ecebae17b7cfe2168b6313be45ad5b04d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="4e6a5-102">&lt;supportPortability&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="4e6a5-103">Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="4e6a5-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-104">\<configuration> Element</span></span>  
<span data-ttu-id="4e6a5-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-105">\<runtime> Element</span></span>  
<span data-ttu-id="4e6a5-106">\<assemblyBinding > elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="4e6a5-107">\<supportPortability > elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e6a5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e6a5-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e6a5-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4e6a5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4e6a5-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e6a5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4e6a5-111">Attributes</span></span>  
  
|<span data-ttu-id="4e6a5-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="4e6a5-112">Attribute</span></span>|<span data-ttu-id="4e6a5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e6a5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e6a5-114">PKT</span><span class="sxs-lookup"><span data-stu-id="4e6a5-114">PKT</span></span>|<span data-ttu-id="4e6a5-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="4e6a5-116">Especifica el token de clave pública del ensamblado afectado, como una cadena.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="4e6a5-117">enabled</span><span class="sxs-lookup"><span data-stu-id="4e6a5-117">enabled</span></span>|<span data-ttu-id="4e6a5-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4e6a5-119">Especifica si se debería habilitar el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4e6a5-120">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4e6a5-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="4e6a5-121">Valor</span><span class="sxs-lookup"><span data-stu-id="4e6a5-121">Value</span></span>|<span data-ttu-id="4e6a5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e6a5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e6a5-123">true</span><span class="sxs-lookup"><span data-stu-id="4e6a5-123">true</span></span>|<span data-ttu-id="4e6a5-124">Habilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="4e6a5-125">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-125">This is the default.</span></span>|  
|<span data-ttu-id="4e6a5-126">false</span><span class="sxs-lookup"><span data-stu-id="4e6a5-126">false</span></span>|<span data-ttu-id="4e6a5-127">Deshabilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="4e6a5-128">Esto permite a la aplicación tener referencias a varias implementaciones del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e6a5-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4e6a5-129">Child Elements</span></span>  
 <span data-ttu-id="4e6a5-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e6a5-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4e6a5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="4e6a5-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e6a5-132">Element</span></span>|<span data-ttu-id="4e6a5-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e6a5-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4e6a5-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4e6a5-135">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="4e6a5-136">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e6a5-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e6a5-137">Remarks</span></span>  
 <span data-ttu-id="4e6a5-138">A partir del [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], se proporciona automáticamente compatibilidad para las aplicaciones que pueden utilizar cualquiera de las dos implementaciones de .NET Framework, por ejemplo la implementación de .NET Framework o .NET Framework para Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="4e6a5-139">El enlazador del ensamblado considera equivalentes las dos implementaciones de un ensamblado de .NET Framework determinado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="4e6a5-140">En algunos escenarios, esta característica de portabilidad de aplicación produce problemas.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="4e6a5-141">En esos escenarios, se puede usar el elemento `<supportPortability>` para deshabilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="4e6a5-142">Uno de estos escenarios es un ensamblado que tiene que hacer referencia al mismo tiempo a la implementación de .NET Framework y a la implementación de .NET Framework para Silverlight de un ensamblado de referencia determinado.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="4e6a5-143">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia a la implementación del escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye en la implementación de Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="4e6a5-144">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="4e6a5-145">Este elemento deshabilita el comportamiento predeterminado y permite que la compilación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e6a5-146">Para que el compilador pase la información a la lógica de enlace del ensamblado de Common Language Runtime, debe usar la opción de compilador `/appconfig` para especificar la ubicación del archivo app.config que contiene este elemento.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e6a5-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e6a5-147">Example</span></span>  
 <span data-ttu-id="4e6a5-148">El siguiente ejemplo permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="4e6a5-149">Se debe usar la opción de compilador `/appconfig` para especificar la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="4e6a5-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e6a5-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e6a5-150">See Also</span></span>  
 [<span data-ttu-id="4e6a5-151">/appconfig (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4e6a5-151">/appconfig (C# Compiler Options)</span></span>](http://msdn.microsoft.com/library/ee523958.aspx)  
 [<span data-ttu-id="4e6a5-152">Introducción de unificación de ensamblados de .NET framework</span><span class="sxs-lookup"><span data-stu-id="4e6a5-152">.NET Framework Assembly Unification Overview</span></span>](http://msdn.microsoft.com/en-us/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)

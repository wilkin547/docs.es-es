---
description: 'Más información acerca de: <supportPortability> elemento'
title: <supportPortability> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 5a39f946d5b3841af5f4254cc2f70142aa6c013d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754516"
---
# <a name="supportportability-element"></a><span data-ttu-id="9e66d-103">\<supportPortability> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9e66d-103">\<supportPortability> Element</span></span>

<span data-ttu-id="9e66d-104">Especifica que una aplicación puede hacer referencia al mismo ensamblado en dos implementaciones diferentes de .NET Framework, deshabilitando el comportamiento predeterminado que trata los ensamblados como equivalentes para los propósitos de portabilidad de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e66d-104">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
## <a name="syntax"></a><span data-ttu-id="9e66d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e66d-105">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e66d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9e66d-106">Attributes and Elements</span></span>  

<span data-ttu-id="9e66d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9e66d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e66d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e66d-108">Attributes</span></span>  
  
|<span data-ttu-id="9e66d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="9e66d-109">Attribute</span></span>|<span data-ttu-id="9e66d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e66d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e66d-111">PKT</span><span class="sxs-lookup"><span data-stu-id="9e66d-111">PKT</span></span>|<span data-ttu-id="9e66d-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9e66d-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="9e66d-113">Especifica el token de clave pública del ensamblado afectado, como una cadena.</span><span class="sxs-lookup"><span data-stu-id="9e66d-113">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="9e66d-114">enabled</span><span class="sxs-lookup"><span data-stu-id="9e66d-114">enabled</span></span>|<span data-ttu-id="9e66d-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="9e66d-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9e66d-116">Especifica si se debería habilitar el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-116">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9e66d-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="9e66d-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="9e66d-118">Value</span><span class="sxs-lookup"><span data-stu-id="9e66d-118">Value</span></span>|<span data-ttu-id="9e66d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e66d-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e66d-120">true</span><span class="sxs-lookup"><span data-stu-id="9e66d-120">true</span></span>|<span data-ttu-id="9e66d-121">Habilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-121">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9e66d-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-122">This is the default.</span></span>|  
|<span data-ttu-id="9e66d-123">false</span><span class="sxs-lookup"><span data-stu-id="9e66d-123">false</span></span>|<span data-ttu-id="9e66d-124">Deshabilita el soporte para la portabilidad entre las implementaciones del ensamblado de .NET Framework especificado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-124">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="9e66d-125">Esto permite a la aplicación tener referencias a varias implementaciones del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-125">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e66d-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9e66d-126">Child Elements</span></span>  

<span data-ttu-id="9e66d-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9e66d-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e66d-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9e66d-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9e66d-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e66d-129">Element</span></span>|<span data-ttu-id="9e66d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e66d-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e66d-131">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e66d-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9e66d-132">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9e66d-132">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="9e66d-133">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e66d-133">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e66d-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9e66d-134">Remarks</span></span>  

<span data-ttu-id="9e66d-135">A partir de la .NET Framework 4, se proporciona automáticamente compatibilidad para las aplicaciones que pueden utilizar cualquiera de las dos implementaciones de la .NET Framework, por ejemplo, la implementación de .NET Framework o la .NET Framework para la implementación de Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9e66d-135">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="9e66d-136">El enlazador del ensamblado considera equivalentes las dos implementaciones de un ensamblado de .NET Framework determinado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-136">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="9e66d-137">En algunos escenarios, esta característica de portabilidad de aplicación produce problemas.</span><span class="sxs-lookup"><span data-stu-id="9e66d-137">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="9e66d-138">En esos escenarios, se puede usar el elemento `<supportPortability>` para deshabilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="9e66d-138">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="9e66d-139">Uno de estos escenarios es un ensamblado que tiene que hacer referencia al mismo tiempo a la implementación de .NET Framework y a la implementación de .NET Framework para Silverlight de un ensamblado de referencia determinado.</span><span class="sxs-lookup"><span data-stu-id="9e66d-139">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="9e66d-140">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia a la implementación del escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye en la implementación de Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9e66d-140">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="9e66d-141">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9e66d-141">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="9e66d-142">Este elemento deshabilita el comportamiento predeterminado y permite que la compilación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="9e66d-142">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9e66d-143">Para que el compilador pase la información a la lógica de enlace del ensamblado de Common Language Runtime, debe usar la opción de compilador `/appconfig` para especificar la ubicación del archivo app.config que contiene este elemento.</span><span class="sxs-lookup"><span data-stu-id="9e66d-143">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e66d-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e66d-144">Example</span></span>  

<span data-ttu-id="9e66d-145">El siguiente ejemplo permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="9e66d-145">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="9e66d-146">Se debe usar la opción de compilador `/appconfig` para especificar la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="9e66d-146">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e66d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e66d-147">See also</span></span>

- [<span data-ttu-id="9e66d-148">-appconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="9e66d-148">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="9e66d-149">[Información general sobre la unificación de ensamblados de .NET Framework](/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9e66d-149">[.NET Framework Assembly Unification Overview](/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>

---
description: 'Más información sobre: <Subtypes> elemento (.net Native)'
title: <Subtypes> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: fb854070-248b-46cf-9dab-c322e2b4d624
ms.openlocfilehash: d30bb482e784d912d3f5d61f688ed2b824e45f27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801961"
---
# <a name="subtypes-element-net-native"></a><span data-ttu-id="28c5e-103">\<Subtypes> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="28c5e-103">\<Subtypes> Element (.NET Native)</span></span>

<span data-ttu-id="28c5e-104">Aplica la directiva en tiempo de ejecución a todas las clases heredadas del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="28c5e-104">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28c5e-105">Syntax</span></span>  
  
```xml  
<Subtypes Activate="policy_type"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type"
          DataContractSerializer="policy_setting"  
          DataContractJsonSerializer="policy_setting"  
          XmlSerializer="policy_setting"  
          MarshalObject="policy_setting"  
          MarshalDelegate="policy_setting"  
          MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28c5e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28c5e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="28c5e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28c5e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28c5e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="28c5e-108">Attributes</span></span>  
  
|<span data-ttu-id="28c5e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="28c5e-109">Attribute</span></span>|<span data-ttu-id="28c5e-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="28c5e-110">Attribute type</span></span>|<span data-ttu-id="28c5e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="28c5e-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="28c5e-112">Reflexión</span><span class="sxs-lookup"><span data-stu-id="28c5e-112">Reflection</span></span>|<span data-ttu-id="28c5e-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-113">Optional attribute.</span></span> <span data-ttu-id="28c5e-114">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="28c5e-114">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="28c5e-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="28c5e-115">Reflection</span></span>|<span data-ttu-id="28c5e-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-116">Optional attribute.</span></span> <span data-ttu-id="28c5e-117">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="28c5e-117">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="28c5e-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="28c5e-118">Reflection</span></span>|<span data-ttu-id="28c5e-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-119">Optional attribute.</span></span> <span data-ttu-id="28c5e-120">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="28c5e-120">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="28c5e-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="28c5e-121">Serialization</span></span>|<span data-ttu-id="28c5e-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-122">Optional attribute.</span></span> <span data-ttu-id="28c5e-123">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="28c5e-123">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="28c5e-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="28c5e-124">Serialization</span></span>|<span data-ttu-id="28c5e-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-125">Optional attribute.</span></span> <span data-ttu-id="28c5e-126">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28c5e-126">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="28c5e-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="28c5e-127">Serialization</span></span>|<span data-ttu-id="28c5e-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-128">Optional attribute.</span></span> <span data-ttu-id="28c5e-129">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28c5e-129">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="28c5e-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="28c5e-130">Serialization</span></span>|<span data-ttu-id="28c5e-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-131">Optional attribute.</span></span> <span data-ttu-id="28c5e-132">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28c5e-132">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="28c5e-133">Interop</span><span class="sxs-lookup"><span data-stu-id="28c5e-133">Interop</span></span>|<span data-ttu-id="28c5e-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-134">Optional attribute.</span></span> <span data-ttu-id="28c5e-135">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="28c5e-135">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="28c5e-136">Interop</span><span class="sxs-lookup"><span data-stu-id="28c5e-136">Interop</span></span>|<span data-ttu-id="28c5e-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-137">Optional attribute.</span></span> <span data-ttu-id="28c5e-138">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="28c5e-138">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="28c5e-139">Interop</span><span class="sxs-lookup"><span data-stu-id="28c5e-139">Interop</span></span>|<span data-ttu-id="28c5e-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="28c5e-140">Optional attribute.</span></span> <span data-ttu-id="28c5e-141">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="28c5e-141">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="28c5e-142">Todos los atributos</span><span class="sxs-lookup"><span data-stu-id="28c5e-142">All attributes</span></span>  
  
|<span data-ttu-id="28c5e-143">Value</span><span class="sxs-lookup"><span data-stu-id="28c5e-143">Value</span></span>|<span data-ttu-id="28c5e-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="28c5e-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28c5e-145">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="28c5e-145">*policy_setting*</span></span>|<span data-ttu-id="28c5e-146">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="28c5e-146">The setting to apply to this policy type.</span></span> <span data-ttu-id="28c5e-147">Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="28c5e-147">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="28c5e-148">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="28c5e-148">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28c5e-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28c5e-149">Child Elements</span></span>  

 <span data-ttu-id="28c5e-150">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28c5e-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28c5e-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28c5e-151">Parent Elements</span></span>  
  
|<span data-ttu-id="28c5e-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="28c5e-152">Element</span></span>|<span data-ttu-id="28c5e-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="28c5e-153">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="28c5e-154">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="28c5e-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28c5e-155">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28c5e-155">Remarks</span></span>  

 <span data-ttu-id="28c5e-156">El elemento `<Subtypes>` aplica la directiva a todos los subtipos de su tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="28c5e-156">The `<Subtypes>` element applies policy to all the subtypes of its containing type.</span></span> <span data-ttu-id="28c5e-157">Se usa cuando se quieren aplicar directivas distintas a los tipos derivados y sus clases base.</span><span class="sxs-lookup"><span data-stu-id="28c5e-157">You use it when you want to apply different policies to derived types and their base classes.</span></span>  
  
 <span data-ttu-id="28c5e-158">Todos los atributos de reflexión, serialización e interoperabilidad son opcionales, aunque al menos uno debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="28c5e-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28c5e-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28c5e-159">Example</span></span>  

 <span data-ttu-id="28c5e-160">En el siguiente ejemplo se define una clase denominada `BaseClass` y una subclase denominada `Derived1`.</span><span class="sxs-lookup"><span data-stu-id="28c5e-160">The following example defines a class named `BaseClass` and a subclass named `Derived1`.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#4)]  
  
 <span data-ttu-id="28c5e-161">Como se muestra en el siguiente código, el archivo de directivas en tiempo de ejecución establece explícitamente las directivas `Dynamic` y `Activate` para `BaseClass` en `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="28c5e-161">As shown in the following code, the runtime directives file explicitly sets the `Dynamic` and `Activate` policies for `BaseClass` to `Excluded`.</span></span> <span data-ttu-id="28c5e-162">Debido a esto, no se pueden crear instancias de los objetos de tipo `BaseClass` ni dinámicamente ni mediante llamadas al constructor de clases `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="28c5e-162">Because of this, objects of type `BaseClass` cannot be instantiated dynamically or by calls to the `BaseClass` class constructor.</span></span> <span data-ttu-id="28c5e-163">Sin embargo, el elemento `<Subtypes>` permite que se puedan crear instancias de las clases derivadas de `BaseClass` tanto dinámicamente como a través de llamadas a sus constructores de clases.</span><span class="sxs-lookup"><span data-stu-id="28c5e-163">However, the `<Subtypes>` element allows classes derived from `BaseClass` to be instantiated dynamically and through calls to their class constructors.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
   <Assembly Name="*Application*" Dynamic="Required All" />  
     <Type Name="Examples.Libraries.BaseClass" Activate ="Excluded" Dynamic="Excluded" >  
        <Subtypes Activate="Public" Dynamic ="Public"/>  
     </Type>  
  </Application>  
</Directives>  
```  
  
 <span data-ttu-id="28c5e-164">Debido a la directiva `<Subtypes>`, el siguiente código, que crea una instancia de `Derived1` dinámicamente mediante una llamada al método <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType>, se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="28c5e-164">Because of the `<Subtypes>` directive, the following code that instantiates a `Derived1` instance dynamically by calling the <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> method executes successfully.</span></span>  <span data-ttu-id="28c5e-165">Aquí, la variable de bloque es un objeto <xref:System.Windows.Controls.TextBlock> en una aplicación de la Tienda Windows en blanco.</span><span class="sxs-lookup"><span data-stu-id="28c5e-165">The block variable here is a <xref:System.Windows.Controls.TextBlock> object in a blank Windows Store app.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="28c5e-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c5e-166">See also</span></span>

- [<span data-ttu-id="28c5e-167">Elemento \<Type></span><span class="sxs-lookup"><span data-stu-id="28c5e-167">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="28c5e-168">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="28c5e-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="28c5e-169">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="28c5e-169">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="28c5e-170">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="28c5e-170">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)

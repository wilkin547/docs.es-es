---
title: Elemento &lt;Property&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ed75d377814a740edece2b6a69e44acbd8ef0c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676816"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="15597-102">Elemento &lt;Property&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="15597-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="15597-103">Aplica la directiva de reflexión en tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="15597-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15597-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15597-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15597-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15597-105">Attributes and Elements</span></span>  
 <span data-ttu-id="15597-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15597-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15597-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="15597-107">Attributes</span></span>  
  
|<span data-ttu-id="15597-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="15597-108">Attribute</span></span>|<span data-ttu-id="15597-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="15597-109">Attribute type</span></span>|<span data-ttu-id="15597-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="15597-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="15597-111">General</span><span class="sxs-lookup"><span data-stu-id="15597-111">General</span></span>|<span data-ttu-id="15597-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="15597-112">Required attribute.</span></span> <span data-ttu-id="15597-113">Especifica el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15597-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="15597-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="15597-114">Reflection</span></span>|<span data-ttu-id="15597-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="15597-115">Optional attribute.</span></span> <span data-ttu-id="15597-116">Controla la consulta para obtener información acerca de la propiedad o la enumeración de la propiedad, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15597-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="15597-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="15597-117">Reflection</span></span>|<span data-ttu-id="15597-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="15597-118">Optional attribute.</span></span> <span data-ttu-id="15597-119">Controla el acceso en tiempo de ejecución a la propiedad para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="15597-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="15597-120">Esta directiva garantiza que una propiedad se puede establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15597-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="15597-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="15597-121">Serialization</span></span>|<span data-ttu-id="15597-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="15597-122">Optional attribute.</span></span> <span data-ttu-id="15597-123">Controla el acceso en tiempo de ejecución a una propiedad para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar instancias de tipo o que estas puedan usarse para enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="15597-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="15597-124">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="15597-124">Name attribute</span></span>  
  
|<span data-ttu-id="15597-125">Valor</span><span class="sxs-lookup"><span data-stu-id="15597-125">Value</span></span>|<span data-ttu-id="15597-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="15597-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="15597-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="15597-127">*method_name*</span></span>|<span data-ttu-id="15597-128">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15597-128">The property name.</span></span> <span data-ttu-id="15597-129">El tipo de la propiedad se define mediante el elemento primario [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="15597-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="15597-130">Todos los demás atributos</span><span class="sxs-lookup"><span data-stu-id="15597-130">All other attributes</span></span>  
  
|<span data-ttu-id="15597-131">Valor</span><span class="sxs-lookup"><span data-stu-id="15597-131">Value</span></span>|<span data-ttu-id="15597-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="15597-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="15597-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="15597-133">*policy_setting*</span></span>|<span data-ttu-id="15597-134">Configuración que se aplica a este tipo de directiva para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15597-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="15597-135">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="15597-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="15597-136">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="15597-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15597-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15597-137">Child Elements</span></span>  
 <span data-ttu-id="15597-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15597-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15597-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15597-139">Parent Elements</span></span>  
  
|<span data-ttu-id="15597-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="15597-140">Element</span></span>|<span data-ttu-id="15597-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="15597-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15597-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="15597-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="15597-143">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="15597-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="15597-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="15597-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="15597-145">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="15597-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15597-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15597-146">Remarks</span></span>  
 <span data-ttu-id="15597-147">Si la directiva de una propiedad no está definida explícitamente, hereda la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="15597-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15597-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15597-148">Example</span></span>  
 <span data-ttu-id="15597-149">En el siguiente ejemplo se usa la reflexión para crear instancias de un objeto `Book` y mostrar sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="15597-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="15597-150">El archivo default.rd.xml original del proyecto se muestra así:</span><span class="sxs-lookup"><span data-stu-id="15597-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="15597-151">El archivo se aplica el valor `All` a la directiva `Activate` de la clase `Book`, lo que permite el acceso a los constructores de clase mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="15597-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="15597-152">La directiva `Browse` para la `Book` clase se hereda de su espacio de nombres primario.</span><span class="sxs-lookup"><span data-stu-id="15597-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="15597-153">Esto se establece en `Required Public`, que hace que los metadatos estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15597-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="15597-154">A continuación se muestra el código fuente del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15597-154">The following is the source code for the example.</span></span> <span data-ttu-id="15597-155">La variable `outputBlock` representa un control [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx).</span><span class="sxs-lookup"><span data-stu-id="15597-155">The `outputBlock` variable represents a [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="15597-156">Sin embargo, compilar y ejecutar este ejemplo genera una excepción [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="15597-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="15597-157">Aunque hemos puesto a disposición los metadatos correspondientes a `Book`, no hemos podido llevar a cabo las implementaciones de los captadores de propiedades disponibles dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="15597-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="15597-158">Podemos corregir este error mediante una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="15597-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="15597-159">Definiendo la directiva `Dynamic` para el tipo `Book` en su elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="15597-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="15597-160">Agregando un elemento [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) anidado por cada propiedad cuyo captador se quiere invocar, como sucede en el siguiente archivo default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="15597-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="15597-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="15597-161">See Also</span></span>  
 [<span data-ttu-id="15597-162">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="15597-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="15597-163">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="15597-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 <span data-ttu-id="15597-164">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="15597-164">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>

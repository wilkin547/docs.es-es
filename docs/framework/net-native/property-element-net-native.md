---
description: 'Más información sobre: <Property> elemento (.net Native)'
title: <Property> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: cd3c033fd2ce21b69ff0d8563f0782838f39b09f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738473"
---
# <a name="property-element-net-native"></a><span data-ttu-id="0c925-103">\<Property> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0c925-103">\<Property> Element (.NET Native)</span></span>

<span data-ttu-id="0c925-104">Aplica la directiva de reflexión en tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c925-104">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c925-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c925-105">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c925-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c925-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0c925-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c925-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c925-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c925-108">Attributes</span></span>  
  
|<span data-ttu-id="0c925-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0c925-109">Attribute</span></span>|<span data-ttu-id="0c925-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="0c925-110">Attribute type</span></span>|<span data-ttu-id="0c925-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c925-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0c925-112">General</span><span class="sxs-lookup"><span data-stu-id="0c925-112">General</span></span>|<span data-ttu-id="0c925-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0c925-113">Required attribute.</span></span> <span data-ttu-id="0c925-114">Especifica el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c925-114">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="0c925-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c925-115">Reflection</span></span>|<span data-ttu-id="0c925-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c925-116">Optional attribute.</span></span> <span data-ttu-id="0c925-117">Controla la consulta para obtener información acerca de la propiedad o la enumeración de la propiedad, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c925-117">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0c925-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c925-118">Reflection</span></span>|<span data-ttu-id="0c925-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c925-119">Optional attribute.</span></span> <span data-ttu-id="0c925-120">Controla el acceso en tiempo de ejecución a la propiedad para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="0c925-120">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="0c925-121">Esta directiva garantiza que una propiedad se puede establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c925-121">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="0c925-122">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c925-122">Serialization</span></span>|<span data-ttu-id="0c925-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c925-123">Optional attribute.</span></span> <span data-ttu-id="0c925-124">Controla el acceso en tiempo de ejecución a una propiedad para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar instancias de tipo o que estas puedan usarse para enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="0c925-124">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0c925-125">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="0c925-125">Name attribute</span></span>  
  
|<span data-ttu-id="0c925-126">Value</span><span class="sxs-lookup"><span data-stu-id="0c925-126">Value</span></span>|<span data-ttu-id="0c925-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c925-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c925-128">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0c925-128">*method_name*</span></span>|<span data-ttu-id="0c925-129">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c925-129">The property name.</span></span> <span data-ttu-id="0c925-130">El tipo de la propiedad se define mediante el [\<Type>](type-element-net-native.md) elemento primario o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="0c925-130">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0c925-131">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="0c925-131">All other attributes</span></span>  
  
|<span data-ttu-id="0c925-132">Value</span><span class="sxs-lookup"><span data-stu-id="0c925-132">Value</span></span>|<span data-ttu-id="0c925-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c925-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c925-134">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0c925-134">*policy_setting*</span></span>|<span data-ttu-id="0c925-135">Configuración que se aplica a este tipo de directiva para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c925-135">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="0c925-136">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="0c925-136">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0c925-137">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="0c925-137">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c925-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c925-138">Child Elements</span></span>  

 <span data-ttu-id="0c925-139">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0c925-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c925-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c925-140">Parent Elements</span></span>  
  
|<span data-ttu-id="0c925-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c925-141">Element</span></span>|<span data-ttu-id="0c925-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c925-142">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="0c925-143">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="0c925-143">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="0c925-144">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="0c925-144">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c925-145">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c925-145">Remarks</span></span>  

 <span data-ttu-id="0c925-146">Si la directiva de una propiedad no está definida explícitamente, hereda la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="0c925-146">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c925-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c925-147">Example</span></span>  

 <span data-ttu-id="0c925-148">En el siguiente ejemplo se usa la reflexión para crear instancias de un objeto `Book` y mostrar sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="0c925-148">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="0c925-149">El archivo default.rd.xml original del proyecto se muestra así:</span><span class="sxs-lookup"><span data-stu-id="0c925-149">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="0c925-150">El archivo se aplica el valor `All` a la directiva `Activate` de la clase `Book`, lo que permite el acceso a los constructores de clase mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="0c925-150">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="0c925-151">La directiva `Browse` para la `Book` clase se hereda de su espacio de nombres primario.</span><span class="sxs-lookup"><span data-stu-id="0c925-151">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="0c925-152">Esto se establece en `Required Public`, que hace que los metadatos estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c925-152">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="0c925-153">A continuación se muestra el código fuente del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c925-153">The following is the source code for the example.</span></span> <span data-ttu-id="0c925-154">La `outputBlock` variable representa un <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="0c925-154">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="0c925-155">Sin embargo, compilar y ejecutar este ejemplo genera una excepción [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="0c925-155">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="0c925-156">Aunque hemos puesto a disposición los metadatos correspondientes a `Book`, no hemos podido llevar a cabo las implementaciones de los captadores de propiedades disponibles dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="0c925-156">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="0c925-157">Podemos corregir este error mediante una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="0c925-157">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="0c925-158">definiendo la `Dynamic` Directiva para el `Book` tipo en su [\<Type>](type-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="0c925-158">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="0c925-159">Agregando un elemento anidado [\<Property>](property-element-net-native.md) para cada propiedad cuyo captador queremos invocar, como hace el siguiente archivo de default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="0c925-159">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c925-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c925-160">See also</span></span>

- [<span data-ttu-id="0c925-161">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0c925-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0c925-162">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c925-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="0c925-163">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c925-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)

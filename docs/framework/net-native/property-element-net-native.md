---
title: <Property> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: a0bdf95a1d1cadf7423f8c6595add13eda4d0d9a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250858"
---
# <a name="property-element-net-native"></a><span data-ttu-id="e467c-102">\<Property> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="e467c-102">\<Property> Element (.NET Native)</span></span>

<span data-ttu-id="e467c-103">Aplica la directiva de reflexión en tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="e467c-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e467c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e467c-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e467c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e467c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e467c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e467c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e467c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e467c-107">Attributes</span></span>  
  
|<span data-ttu-id="e467c-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e467c-108">Attribute</span></span>|<span data-ttu-id="e467c-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="e467c-109">Attribute type</span></span>|<span data-ttu-id="e467c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e467c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="e467c-111">General</span><span class="sxs-lookup"><span data-stu-id="e467c-111">General</span></span>|<span data-ttu-id="e467c-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e467c-112">Required attribute.</span></span> <span data-ttu-id="e467c-113">Especifica el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e467c-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="e467c-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="e467c-114">Reflection</span></span>|<span data-ttu-id="e467c-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e467c-115">Optional attribute.</span></span> <span data-ttu-id="e467c-116">Controla la consulta para obtener información acerca de la propiedad o la enumeración de la propiedad, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e467c-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="e467c-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="e467c-117">Reflection</span></span>|<span data-ttu-id="e467c-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e467c-118">Optional attribute.</span></span> <span data-ttu-id="e467c-119">Controla el acceso en tiempo de ejecución a la propiedad para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="e467c-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="e467c-120">Esta directiva garantiza que una propiedad se puede establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e467c-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="e467c-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="e467c-121">Serialization</span></span>|<span data-ttu-id="e467c-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e467c-122">Optional attribute.</span></span> <span data-ttu-id="e467c-123">Controla el acceso en tiempo de ejecución a una propiedad para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar instancias de tipo o que estas puedan usarse para enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="e467c-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="e467c-124">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="e467c-124">Name attribute</span></span>  
  
|<span data-ttu-id="e467c-125">Valor</span><span class="sxs-lookup"><span data-stu-id="e467c-125">Value</span></span>|<span data-ttu-id="e467c-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="e467c-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e467c-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="e467c-127">*method_name*</span></span>|<span data-ttu-id="e467c-128">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e467c-128">The property name.</span></span> <span data-ttu-id="e467c-129">El tipo de la propiedad se define mediante el [\<Type>](type-element-net-native.md) elemento primario o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="e467c-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="e467c-130">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="e467c-130">All other attributes</span></span>  
  
|<span data-ttu-id="e467c-131">Valor</span><span class="sxs-lookup"><span data-stu-id="e467c-131">Value</span></span>|<span data-ttu-id="e467c-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e467c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e467c-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="e467c-133">*policy_setting*</span></span>|<span data-ttu-id="e467c-134">Configuración que se aplica a este tipo de directiva para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e467c-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="e467c-135">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="e467c-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="e467c-136">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="e467c-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e467c-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e467c-137">Child Elements</span></span>  

 <span data-ttu-id="e467c-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e467c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e467c-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e467c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="e467c-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="e467c-140">Element</span></span>|<span data-ttu-id="e467c-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="e467c-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="e467c-142">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e467c-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="e467c-143">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e467c-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e467c-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e467c-144">Remarks</span></span>  

 <span data-ttu-id="e467c-145">Si la directiva de una propiedad no está definida explícitamente, hereda la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="e467c-145">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e467c-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e467c-146">Example</span></span>  

 <span data-ttu-id="e467c-147">En el siguiente ejemplo se usa la reflexión para crear instancias de un objeto `Book` y mostrar sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e467c-147">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="e467c-148">El archivo default.rd.xml original del proyecto se muestra así:</span><span class="sxs-lookup"><span data-stu-id="e467c-148">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="e467c-149">El archivo se aplica el valor `All` a la directiva `Activate` de la clase `Book`, lo que permite el acceso a los constructores de clase mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="e467c-149">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="e467c-150">La directiva `Browse` para la `Book` clase se hereda de su espacio de nombres primario.</span><span class="sxs-lookup"><span data-stu-id="e467c-150">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="e467c-151">Esto se establece en `Required Public`, que hace que los metadatos estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e467c-151">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="e467c-152">A continuación se muestra el código fuente del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e467c-152">The following is the source code for the example.</span></span> <span data-ttu-id="e467c-153">La `outputBlock` variable representa un <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="e467c-153">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="e467c-154">Sin embargo, compilar y ejecutar este ejemplo genera una excepción [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="e467c-154">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="e467c-155">Aunque hemos puesto a disposición los metadatos correspondientes a `Book`, no hemos podido llevar a cabo las implementaciones de los captadores de propiedades disponibles dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="e467c-155">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="e467c-156">Podemos corregir este error mediante una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="e467c-156">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="e467c-157">definiendo la `Dynamic` Directiva para el `Book` tipo en su [\<Type>](type-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e467c-157">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="e467c-158">Agregando un elemento anidado [\<Property>](property-element-net-native.md) para cada propiedad cuyo captador queremos invocar, como hace el siguiente archivo de default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="e467c-158">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e467c-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="e467c-159">See also</span></span>

- [<span data-ttu-id="e467c-160">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="e467c-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e467c-161">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e467c-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="e467c-162">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e467c-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)

---
title: <Property> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20657e0a583890b851ab8e15c50bce791a3641b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61866774"
---
# <a name="property-element-net-native"></a><span data-ttu-id="37f5b-102">\<Propiedad > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="37f5b-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="37f5b-103">Aplica la directiva de reflexión en tiempo de ejecución a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="37f5b-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f5b-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37f5b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37f5b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37f5b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37f5b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37f5b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="37f5b-107">Attributes</span></span>  
  
|<span data-ttu-id="37f5b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="37f5b-108">Attribute</span></span>|<span data-ttu-id="37f5b-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="37f5b-109">Attribute type</span></span>|<span data-ttu-id="37f5b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f5b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="37f5b-111">General</span><span class="sxs-lookup"><span data-stu-id="37f5b-111">General</span></span>|<span data-ttu-id="37f5b-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="37f5b-112">Required attribute.</span></span> <span data-ttu-id="37f5b-113">Especifica el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="37f5b-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="37f5b-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="37f5b-114">Reflection</span></span>|<span data-ttu-id="37f5b-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="37f5b-115">Optional attribute.</span></span> <span data-ttu-id="37f5b-116">Controla la consulta para obtener información acerca de la propiedad o la enumeración de la propiedad, pero no permite el acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37f5b-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="37f5b-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="37f5b-117">Reflection</span></span>|<span data-ttu-id="37f5b-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="37f5b-118">Optional attribute.</span></span> <span data-ttu-id="37f5b-119">Controla el acceso en tiempo de ejecución a la propiedad para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="37f5b-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="37f5b-120">Esta directiva garantiza que una propiedad se puede establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37f5b-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="37f5b-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="37f5b-121">Serialization</span></span>|<span data-ttu-id="37f5b-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="37f5b-122">Optional attribute.</span></span> <span data-ttu-id="37f5b-123">Controla el acceso en tiempo de ejecución a una propiedad para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar instancias de tipo o que estas puedan usarse para enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="37f5b-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="37f5b-124">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="37f5b-124">Name attribute</span></span>  
  
|<span data-ttu-id="37f5b-125">Valor</span><span class="sxs-lookup"><span data-stu-id="37f5b-125">Value</span></span>|<span data-ttu-id="37f5b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f5b-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37f5b-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="37f5b-127">*method_name*</span></span>|<span data-ttu-id="37f5b-128">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="37f5b-128">The property name.</span></span> <span data-ttu-id="37f5b-129">El tipo de la propiedad se define mediante el elemento primario [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="37f5b-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="37f5b-130">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="37f5b-130">All other attributes</span></span>  
  
|<span data-ttu-id="37f5b-131">Valor</span><span class="sxs-lookup"><span data-stu-id="37f5b-131">Value</span></span>|<span data-ttu-id="37f5b-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f5b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37f5b-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="37f5b-133">*policy_setting*</span></span>|<span data-ttu-id="37f5b-134">Configuración que se aplica a este tipo de directiva para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="37f5b-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="37f5b-135">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="37f5b-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="37f5b-136">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="37f5b-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37f5b-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37f5b-137">Child Elements</span></span>  
 <span data-ttu-id="37f5b-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37f5b-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37f5b-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37f5b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="37f5b-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f5b-140">Element</span></span>|<span data-ttu-id="37f5b-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f5b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f5b-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="37f5b-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="37f5b-143">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="37f5b-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="37f5b-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="37f5b-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="37f5b-145">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="37f5b-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37f5b-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37f5b-146">Remarks</span></span>  
 <span data-ttu-id="37f5b-147">Si la directiva de una propiedad no está definida explícitamente, hereda la directiva en tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="37f5b-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37f5b-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37f5b-148">Example</span></span>  
 <span data-ttu-id="37f5b-149">En el siguiente ejemplo se usa la reflexión para crear instancias de un objeto `Book` y mostrar sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="37f5b-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="37f5b-150">El archivo default.rd.xml original del proyecto se muestra así:</span><span class="sxs-lookup"><span data-stu-id="37f5b-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="37f5b-151">El archivo se aplica el valor `All` a la directiva `Activate` de la clase `Book`, lo que permite el acceso a los constructores de clase mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="37f5b-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="37f5b-152">La directiva `Browse` para la `Book` clase se hereda de su espacio de nombres primario.</span><span class="sxs-lookup"><span data-stu-id="37f5b-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="37f5b-153">Esto se establece en `Required Public`, que hace que los metadatos estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37f5b-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="37f5b-154">A continuación se muestra el código fuente del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37f5b-154">The following is the source code for the example.</span></span> <span data-ttu-id="37f5b-155">El `outputBlock` variable representa un <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="37f5b-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="37f5b-156">Sin embargo, compilar y ejecutar este ejemplo genera una excepción [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="37f5b-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="37f5b-157">Aunque hemos puesto a disposición los metadatos correspondientes a `Book`, no hemos podido llevar a cabo las implementaciones de los captadores de propiedades disponibles dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="37f5b-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="37f5b-158">Podemos corregir este error mediante una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="37f5b-158">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="37f5b-159">Definiendo la directiva `Dynamic` para el tipo `Book` en su elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="37f5b-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="37f5b-160">Agregando un elemento [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) anidado por cada propiedad cuyo captador se quiere invocar, como sucede en el siguiente archivo default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="37f5b-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37f5b-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f5b-161">See also</span></span>

- [<span data-ttu-id="37f5b-162">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="37f5b-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="37f5b-163">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="37f5b-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- <span data-ttu-id="37f5b-164">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="37f5b-164">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>

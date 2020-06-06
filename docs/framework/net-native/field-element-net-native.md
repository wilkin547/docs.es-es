---
title: <Field>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 2a63b88c399a999cd00750dee1614352cea10e80
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128420"
---
# <a name="field-element-net-native"></a><span data-ttu-id="ebe38-102">\<Field>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ebe38-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="ebe38-103">Aplica la directiva de reflexión en tiempo de ejecución a un campo.</span><span class="sxs-lookup"><span data-stu-id="ebe38-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebe38-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebe38-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ebe38-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ebe38-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ebe38-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebe38-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ebe38-107">Attributes</span></span>  
  
|<span data-ttu-id="ebe38-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ebe38-108">Attribute</span></span>|<span data-ttu-id="ebe38-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="ebe38-109">Attribute type</span></span>|<span data-ttu-id="ebe38-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebe38-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ebe38-111">General</span><span class="sxs-lookup"><span data-stu-id="ebe38-111">General</span></span>|<span data-ttu-id="ebe38-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ebe38-112">Required attribute.</span></span> <span data-ttu-id="ebe38-113">Especifica el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="ebe38-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="ebe38-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ebe38-114">Reflection</span></span>|<span data-ttu-id="ebe38-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebe38-115">Optional attribute.</span></span> <span data-ttu-id="ebe38-116">Controla la consulta para obtener información sobre el campo o para enumerar el campo, pero no habilita ningún acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ebe38-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="ebe38-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ebe38-117">Reflection</span></span>|<span data-ttu-id="ebe38-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebe38-118">Optional attribute.</span></span> <span data-ttu-id="ebe38-119">Controla el acceso en tiempo de ejecución al campo para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="ebe38-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="ebe38-120">Esta directiva garantiza que un campo se pueda establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ebe38-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="ebe38-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="ebe38-121">Serialization</span></span>|<span data-ttu-id="ebe38-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebe38-122">Optional attribute.</span></span> <span data-ttu-id="ebe38-123">Controla el acceso en tiempo de ejecución a un campo para permitir que las instancias de tipos puedan ser serializadas por bibliotecas (como el serializador de JSON Newtonsoft) o para que puedan usarse en el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="ebe38-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ebe38-124">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="ebe38-124">Name attribute</span></span>  
  
|<span data-ttu-id="ebe38-125">Value</span><span class="sxs-lookup"><span data-stu-id="ebe38-125">Value</span></span>|<span data-ttu-id="ebe38-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebe38-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ebe38-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="ebe38-127">*method_name*</span></span>|<span data-ttu-id="ebe38-128">Nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="ebe38-128">The field name.</span></span> <span data-ttu-id="ebe38-129">El tipo del campo está definido por el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="ebe38-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ebe38-130">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="ebe38-130">All other attributes</span></span>  
  
|<span data-ttu-id="ebe38-131">Value</span><span class="sxs-lookup"><span data-stu-id="ebe38-131">Value</span></span>|<span data-ttu-id="ebe38-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebe38-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ebe38-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ebe38-133">*policy_setting*</span></span>|<span data-ttu-id="ebe38-134">La configuración que se aplica a este tipo de política para el campo.</span><span class="sxs-lookup"><span data-stu-id="ebe38-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="ebe38-135">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="ebe38-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="ebe38-136">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="ebe38-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebe38-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ebe38-137">Child Elements</span></span>  
 <span data-ttu-id="ebe38-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ebe38-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebe38-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ebe38-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ebe38-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebe38-140">Element</span></span>|<span data-ttu-id="ebe38-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebe38-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="ebe38-142">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ebe38-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="ebe38-143">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ebe38-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebe38-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebe38-144">Remarks</span></span>  
 <span data-ttu-id="ebe38-145">Si la directiva de un campo no se define explícitamente, entonces hereda la directiva de tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="ebe38-145">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe38-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebe38-146">See also</span></span>

- [<span data-ttu-id="ebe38-147">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ebe38-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="ebe38-148">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ebe38-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ebe38-149">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ebe38-149">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)

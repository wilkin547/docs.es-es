---
description: 'Más información sobre: <Field> elemento (.net Native)'
title: <Field> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 1f8c8b6720fb90bdc5855da7b17694253bbb7629
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747847"
---
# <a name="field-element-net-native"></a><span data-ttu-id="db2d9-103">\<Field> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="db2d9-103">\<Field> Element (.NET Native)</span></span>

<span data-ttu-id="db2d9-104">Aplica la directiva de reflexión en tiempo de ejecución a un campo.</span><span class="sxs-lookup"><span data-stu-id="db2d9-104">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2d9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db2d9-105">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db2d9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db2d9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="db2d9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="db2d9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db2d9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="db2d9-108">Attributes</span></span>  
  
|<span data-ttu-id="db2d9-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="db2d9-109">Attribute</span></span>|<span data-ttu-id="db2d9-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="db2d9-110">Attribute type</span></span>|<span data-ttu-id="db2d9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="db2d9-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="db2d9-112">General</span><span class="sxs-lookup"><span data-stu-id="db2d9-112">General</span></span>|<span data-ttu-id="db2d9-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="db2d9-113">Required attribute.</span></span> <span data-ttu-id="db2d9-114">Especifica el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="db2d9-114">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="db2d9-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="db2d9-115">Reflection</span></span>|<span data-ttu-id="db2d9-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="db2d9-116">Optional attribute.</span></span> <span data-ttu-id="db2d9-117">Controla la consulta para obtener información sobre el campo o para enumerar el campo, pero no habilita ningún acceso dinámico en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="db2d9-117">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="db2d9-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="db2d9-118">Reflection</span></span>|<span data-ttu-id="db2d9-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="db2d9-119">Optional attribute.</span></span> <span data-ttu-id="db2d9-120">Controla el acceso en tiempo de ejecución al campo para habilitar la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="db2d9-120">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="db2d9-121">Esta directiva garantiza que un campo se pueda establecer o recuperar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="db2d9-121">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="db2d9-122">Serialización</span><span class="sxs-lookup"><span data-stu-id="db2d9-122">Serialization</span></span>|<span data-ttu-id="db2d9-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="db2d9-123">Optional attribute.</span></span> <span data-ttu-id="db2d9-124">Controla el acceso en tiempo de ejecución a un campo para permitir que las instancias de tipos puedan ser serializadas por bibliotecas (como el serializador de JSON Newtonsoft) o para que puedan usarse en el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="db2d9-124">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="db2d9-125">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="db2d9-125">Name attribute</span></span>  
  
|<span data-ttu-id="db2d9-126">Value</span><span class="sxs-lookup"><span data-stu-id="db2d9-126">Value</span></span>|<span data-ttu-id="db2d9-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="db2d9-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="db2d9-128">*method_name*</span><span class="sxs-lookup"><span data-stu-id="db2d9-128">*method_name*</span></span>|<span data-ttu-id="db2d9-129">Nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="db2d9-129">The field name.</span></span> <span data-ttu-id="db2d9-130">El tipo del campo está definido por el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="db2d9-130">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="db2d9-131">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="db2d9-131">All other attributes</span></span>  
  
|<span data-ttu-id="db2d9-132">Value</span><span class="sxs-lookup"><span data-stu-id="db2d9-132">Value</span></span>|<span data-ttu-id="db2d9-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="db2d9-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="db2d9-134">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="db2d9-134">*policy_setting*</span></span>|<span data-ttu-id="db2d9-135">La configuración que se aplica a este tipo de política para el campo.</span><span class="sxs-lookup"><span data-stu-id="db2d9-135">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="db2d9-136">Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`.</span><span class="sxs-lookup"><span data-stu-id="db2d9-136">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="db2d9-137">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="db2d9-137">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db2d9-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db2d9-138">Child Elements</span></span>  

 <span data-ttu-id="db2d9-139">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="db2d9-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db2d9-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db2d9-140">Parent Elements</span></span>  
  
|<span data-ttu-id="db2d9-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="db2d9-141">Element</span></span>|<span data-ttu-id="db2d9-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="db2d9-142">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="db2d9-143">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="db2d9-143">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="db2d9-144">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="db2d9-144">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db2d9-145">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db2d9-145">Remarks</span></span>  

 <span data-ttu-id="db2d9-146">Si la directiva de un campo no se define explícitamente, entonces hereda la directiva de tiempo de ejecución de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="db2d9-146">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2d9-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="db2d9-147">See also</span></span>

- [<span data-ttu-id="db2d9-148">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="db2d9-148">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="db2d9-149">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="db2d9-149">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="db2d9-150">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="db2d9-150">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)

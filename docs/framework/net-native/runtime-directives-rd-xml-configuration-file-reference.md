---
description: 'Más información sobre: directivas de tiempo de ejecución (rd.xml) referencia del archivo de configuración'
title: Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: 9c995bd831f01e47c651d015895398e1ad42633d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802000"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="754d9-103">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="754d9-103">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="754d9-104">Un archivo de directivas de tiempo de ejecución (.rd.xml) es un archivo de configuración XML que especifica si los elementos de programa designados están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="754d9-104">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="754d9-105">A continuación se muestra un ejemplo de un archivo de directivas de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="754d9-105">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="754d9-106">Estructura de un archivo de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="754d9-106">The structure of a runtime directives file</span></span>

<span data-ttu-id="754d9-107">El archivo de directivas de tiempo de ejecución utiliza el espacio de nombres `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="754d9-107">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="754d9-108">El elemento raíz es [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-108">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="754d9-109">Puede contener cero o más elementos [Library](library-element-net-native.md) y cero o un elemento [Application](application-element-net-native.md), como se muestra en la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="754d9-109">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="754d9-110">Los atributos del elemento [Application](application-element-net-native.md) pueden definir directivas de reflexión en tiempo de ejecución para toda la aplicación, o puede actuar como contenedor de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="754d9-110">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="754d9-111">El elemento [Library](library-element-net-native.md), por otro lado, es simplemente un contenedor.</span><span class="sxs-lookup"><span data-stu-id="754d9-111">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="754d9-112">Los elementos secundarios de los elementos [Application](application-element-net-native.md) y [Library](library-element-net-native.md) definen los tipos, métodos, campos, propiedades y eventos que están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="754d9-112">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="754d9-113">Para obtener información de referencia, seleccione los elementos de la siguiente estructura o vea [Runtime Directive Elements](runtime-directive-elements.md) (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="754d9-113">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="754d9-114">En la siguiente jerarquía, los puntos suspensivos marcan una estructura recursiva.</span><span class="sxs-lookup"><span data-stu-id="754d9-114">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="754d9-115">La información entre paréntesis indica si el elemento es obligatorio u opcional y, si se utiliza, el número de instancias permitidas (una o varias).</span><span class="sxs-lookup"><span data-stu-id="754d9-115">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

- <span data-ttu-id="754d9-116">[Directives](directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-116">[Directives](directives-element-net-native.md) [1:1]</span></span>
  - <span data-ttu-id="754d9-117">[Application](application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-117">[Application](application-element-net-native.md) [0:1]</span></span>
    - <span data-ttu-id="754d9-118">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-118">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-119">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-119">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-120">.</span><span class="sxs-lookup"><span data-stu-id="754d9-120">.</span></span> <span data-ttu-id="754d9-121">.</span><span class="sxs-lookup"><span data-stu-id="754d9-121">.</span></span>
      - <span data-ttu-id="754d9-122">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-122">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-123">.</span><span class="sxs-lookup"><span data-stu-id="754d9-123">.</span></span> <span data-ttu-id="754d9-124">.</span><span class="sxs-lookup"><span data-stu-id="754d9-124">.</span></span>
      - <span data-ttu-id="754d9-125">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-125">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-126">.</span><span class="sxs-lookup"><span data-stu-id="754d9-126">.</span></span> <span data-ttu-id="754d9-127">.</span><span class="sxs-lookup"><span data-stu-id="754d9-127">.</span></span>
    - <span data-ttu-id="754d9-128">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-128">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-129">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-129">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-130">.</span><span class="sxs-lookup"><span data-stu-id="754d9-130">.</span></span> <span data-ttu-id="754d9-131">.</span><span class="sxs-lookup"><span data-stu-id="754d9-131">.</span></span>
      - <span data-ttu-id="754d9-132">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-132">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-133">.</span><span class="sxs-lookup"><span data-stu-id="754d9-133">.</span></span> <span data-ttu-id="754d9-134">.</span><span class="sxs-lookup"><span data-stu-id="754d9-134">.</span></span>
      - <span data-ttu-id="754d9-135">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-135">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-136">.</span><span class="sxs-lookup"><span data-stu-id="754d9-136">.</span></span> <span data-ttu-id="754d9-137">.</span><span class="sxs-lookup"><span data-stu-id="754d9-137">.</span></span>
    - <span data-ttu-id="754d9-138">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-138">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-139">[Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-139">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="754d9-140">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-140">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-141">.</span><span class="sxs-lookup"><span data-stu-id="754d9-141">.</span></span> <span data-ttu-id="754d9-142">.</span><span class="sxs-lookup"><span data-stu-id="754d9-142">.</span></span>
      - <span data-ttu-id="754d9-143">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-143">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-144">.</span><span class="sxs-lookup"><span data-stu-id="754d9-144">.</span></span> <span data-ttu-id="754d9-145">.</span><span class="sxs-lookup"><span data-stu-id="754d9-145">.</span></span>
      - <span data-ttu-id="754d9-146">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-146">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="754d9-147">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-147">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-148">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-148">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-149">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-149">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-150">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-150">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-151">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-151">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-152">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-152">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="754d9-153">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-153">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-154">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-154">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-155">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-155">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="754d9-156">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-156">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="754d9-157">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-157">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-158">.</span><span class="sxs-lookup"><span data-stu-id="754d9-158">.</span></span> <span data-ttu-id="754d9-159">.</span><span class="sxs-lookup"><span data-stu-id="754d9-159">.</span></span>
      - <span data-ttu-id="754d9-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-161">.</span><span class="sxs-lookup"><span data-stu-id="754d9-161">.</span></span> <span data-ttu-id="754d9-162">.</span><span class="sxs-lookup"><span data-stu-id="754d9-162">.</span></span>
      - <span data-ttu-id="754d9-163">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-163">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-164">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-164">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-165">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-165">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="754d9-166">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-166">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-167">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-167">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="754d9-168">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-168">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-169">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-169">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-170">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-170">[Event](event-element-net-native.md) [0:M]</span></span>
  - <span data-ttu-id="754d9-171">[Library](library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-171">[Library](library-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="754d9-172">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-172">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-173">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-173">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-174">.</span><span class="sxs-lookup"><span data-stu-id="754d9-174">.</span></span> <span data-ttu-id="754d9-175">.</span><span class="sxs-lookup"><span data-stu-id="754d9-175">.</span></span>
      - <span data-ttu-id="754d9-176">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-176">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-177">.</span><span class="sxs-lookup"><span data-stu-id="754d9-177">.</span></span> <span data-ttu-id="754d9-178">.</span><span class="sxs-lookup"><span data-stu-id="754d9-178">.</span></span>
      - <span data-ttu-id="754d9-179">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-179">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-180">.</span><span class="sxs-lookup"><span data-stu-id="754d9-180">.</span></span> <span data-ttu-id="754d9-181">.</span><span class="sxs-lookup"><span data-stu-id="754d9-181">.</span></span>
    - <span data-ttu-id="754d9-182">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-182">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-183">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-183">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-184">.</span><span class="sxs-lookup"><span data-stu-id="754d9-184">.</span></span> <span data-ttu-id="754d9-185">.</span><span class="sxs-lookup"><span data-stu-id="754d9-185">.</span></span>
      - <span data-ttu-id="754d9-186">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-186">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-187">.</span><span class="sxs-lookup"><span data-stu-id="754d9-187">.</span></span> <span data-ttu-id="754d9-188">.</span><span class="sxs-lookup"><span data-stu-id="754d9-188">.</span></span>
      - <span data-ttu-id="754d9-189">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-189">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-190">.</span><span class="sxs-lookup"><span data-stu-id="754d9-190">.</span></span> <span data-ttu-id="754d9-191">.</span><span class="sxs-lookup"><span data-stu-id="754d9-191">.</span></span>
    - <span data-ttu-id="754d9-192">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-192">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-193">[Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-193">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="754d9-194">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-194">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-195">.</span><span class="sxs-lookup"><span data-stu-id="754d9-195">.</span></span> <span data-ttu-id="754d9-196">.</span><span class="sxs-lookup"><span data-stu-id="754d9-196">.</span></span>
      - <span data-ttu-id="754d9-197">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-197">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-198">.</span><span class="sxs-lookup"><span data-stu-id="754d9-198">.</span></span> <span data-ttu-id="754d9-199">.</span><span class="sxs-lookup"><span data-stu-id="754d9-199">.</span></span>
      - <span data-ttu-id="754d9-200">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="754d9-200">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="754d9-201">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-201">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-202">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-202">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-203">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-203">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="754d9-204">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-204">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-205">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-205">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-206">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-206">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="754d9-207">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-207">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="754d9-208">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-208">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="754d9-209">.</span><span class="sxs-lookup"><span data-stu-id="754d9-209">.</span></span> <span data-ttu-id="754d9-210">.</span><span class="sxs-lookup"><span data-stu-id="754d9-210">.</span></span>
      - <span data-ttu-id="754d9-211">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="754d9-211">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="754d9-212">.</span><span class="sxs-lookup"><span data-stu-id="754d9-212">.</span></span> <span data-ttu-id="754d9-213">.</span><span class="sxs-lookup"><span data-stu-id="754d9-213">.</span></span>
      - <span data-ttu-id="754d9-214">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-214">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-215">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-215">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="754d9-216">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-216">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-217">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-217">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="754d9-218">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="754d9-218">[Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="754d9-219">El elemento [Application](application-element-net-native.md) no puede tener atributos o puede tener los atributos de directiva tratados en la [sección sobre política y directivas de tiempo de ejecución](#Directives).</span><span class="sxs-lookup"><span data-stu-id="754d9-219">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="754d9-220">Un elemento [Library](library-element-net-native.md) tiene un solo atributo, `Name`, que especifica el nombre de una biblioteca o ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="754d9-220">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="754d9-221">Por ejemplo, el siguiente elemento [Library](library-element-net-native.md) se aplica a un ensamblado denominado Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="754d9-221">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="754d9-222">Política y directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="754d9-222">Runtime directives and policy</span></span>

<span data-ttu-id="754d9-223">El elemento [Application](application-element-net-native.md) y los elementos secundarios de los elementos [Library](library-element-net-native.md) y [Application](application-element-net-native.md) expresan directiva; es decir, definen la forma en que una aplicación puede aplicar reflexión a un elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="754d9-223">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="754d9-224">El tipo de la directiva se define mediante un atributo del elemento (por ejemplo, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="754d9-224">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="754d9-225">El valor de la directiva se define mediante el valor del atributo (por ejemplo, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="754d9-225">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="754d9-226">Cualquier directiva especificada por un atributo de un elemento se aplica a todos los elementos secundarios que no especifican ningún valor para esa directiva.</span><span class="sxs-lookup"><span data-stu-id="754d9-226">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="754d9-227">Por ejemplo, si una directiva se especifica mediante un elemento [Type](type-element-net-native.md), esa directiva se aplica a todos los tipos y miembros contenidos para los que no se especifica explícitamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="754d9-227">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="754d9-228">La directiva que puede expresarse mediante los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) difiere de la que puede expresarse para miembros individuales (mediante los elementos [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) y [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="754d9-228">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="754d9-229">Especificar la directiva para ensamblados, espacios de nombres y tipos</span><span class="sxs-lookup"><span data-stu-id="754d9-229">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="754d9-230">Los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="754d9-230">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="754d9-231">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="754d9-231">`Activate`.</span></span> <span data-ttu-id="754d9-232">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de las instancias.</span><span class="sxs-lookup"><span data-stu-id="754d9-232">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="754d9-233">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-233">`Browse`.</span></span> <span data-ttu-id="754d9-234">Controla la consulta de información sobre elementos del programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="754d9-234">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="754d9-235">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-235">`Dynamic`.</span></span> <span data-ttu-id="754d9-236">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="754d9-236">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="754d9-237">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-237">`Serialize`.</span></span> <span data-ttu-id="754d9-238">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades, para permitir que bibliotecas de terceros (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="754d9-238">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="754d9-239">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="754d9-239">`DataContractSerializer`.</span></span> <span data-ttu-id="754d9-240">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="754d9-240">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="754d9-241">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="754d9-241">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="754d9-242">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="754d9-242">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="754d9-243">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="754d9-243">`XmlSerializer`.</span></span> <span data-ttu-id="754d9-244">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="754d9-244">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="754d9-245">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="754d9-245">`MarshalObject`.</span></span> <span data-ttu-id="754d9-246">Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="754d9-246">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="754d9-247">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="754d9-247">`MarshalDelegate`.</span></span> <span data-ttu-id="754d9-248">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="754d9-248">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="754d9-249">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="754d9-249">`MarshalStructure` .</span></span> <span data-ttu-id="754d9-250">Controla la directiva para calcular referencias de estructuras a código nativo.</span><span class="sxs-lookup"><span data-stu-id="754d9-250">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="754d9-251">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="754d9-251">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="754d9-252">`All`.</span><span class="sxs-lookup"><span data-stu-id="754d9-252">`All`.</span></span> <span data-ttu-id="754d9-253">Habilita la directiva para todos los tipos y miembros que no se eliminan con la cadena de herramientas.</span><span class="sxs-lookup"><span data-stu-id="754d9-253">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="754d9-254">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="754d9-254">`Auto`.</span></span> <span data-ttu-id="754d9-255">Usa el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="754d9-255">Use the default behavior.</span></span> <span data-ttu-id="754d9-256">(No especificar una directiva es equivalente a establecer esa directiva en `Auto`, a menos que se invalide la directiva, por ejemplo, por un elemento primario).</span><span class="sxs-lookup"><span data-stu-id="754d9-256">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="754d9-257">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="754d9-257">`Excluded`.</span></span> <span data-ttu-id="754d9-258">Deshabilita la directiva para el elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="754d9-258">Disable the policy for the program element.</span></span>

- <span data-ttu-id="754d9-259">`Public`.</span><span class="sxs-lookup"><span data-stu-id="754d9-259">`Public`.</span></span> <span data-ttu-id="754d9-260">Habilita la directiva para tipos o miembros públicos a menos que la cadena de herramientas determine que el miembro es innecesario y, por tanto, lo quita.</span><span class="sxs-lookup"><span data-stu-id="754d9-260">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="754d9-261">(En este último caso, debe utilizar `Required Public` para asegurarse de que el miembro se conserva y tiene capacidades de reflexión).</span><span class="sxs-lookup"><span data-stu-id="754d9-261">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="754d9-262">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="754d9-262">`PublicAndInternal`.</span></span> <span data-ttu-id="754d9-263">Habilita la directiva para tipos o miembros públicos e internos si la cadena de herramientas no los quita.</span><span class="sxs-lookup"><span data-stu-id="754d9-263">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="754d9-264">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="754d9-264">`Required Public`.</span></span> <span data-ttu-id="754d9-265">Exige que la cadena de herramientas mantenga los tipos y miembros públicos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="754d9-265">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="754d9-266">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="754d9-266">`Required PublicAndInternal`.</span></span> <span data-ttu-id="754d9-267">Exige que la cadena de herramientas mantenga los tipos y miembros públicos e internos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="754d9-267">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="754d9-268">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="754d9-268">`Required All`.</span></span> <span data-ttu-id="754d9-269">Exige que la cadena de herramientas mantenga todos los tipos y miembros tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="754d9-269">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="754d9-270">Por ejemplo, el siguiente archivo de directivas de tiempo de ejecución define una directiva para todos los tipos y miembros del ensamblado DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="754d9-270">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="754d9-271">Permite reflexión para la serialización de todas las propiedades públicas, permite buscar todos los tipos y miembros de tipo, permite la activación para todos los tipos (debido al atributo `Dynamic`) y permite la reflexión para todos los tipos y miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="754d9-271">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="754d9-272">Especificar la directiva para los miembros</span><span class="sxs-lookup"><span data-stu-id="754d9-272">Specifying policy for members</span></span>

<span data-ttu-id="754d9-273">Los elementos [Property](property-element-net-native.md) y [Field](field-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="754d9-273">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="754d9-274">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="754d9-274">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="754d9-275">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="754d9-275">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="754d9-276">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="754d9-276">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="754d9-277">`Serialize`: controla el acceso en tiempo de ejecución al miembro para permitir que las bibliotecas (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="754d9-277">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="754d9-278">Esta directiva puede aplicarse a propiedades, campos y constructores.</span><span class="sxs-lookup"><span data-stu-id="754d9-278">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="754d9-279">Los elementos [Method](method-element-net-native.md) y [Event](event-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="754d9-279">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="754d9-280">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="754d9-280">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="754d9-281">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="754d9-281">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="754d9-282">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="754d9-282">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="754d9-283">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="754d9-283">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="754d9-284">`Auto`: usar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="754d9-284">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="754d9-285">(No especificar una política es equivalente a establecer esa directiva en `Auto`, a menos que algo la invalide).</span><span class="sxs-lookup"><span data-stu-id="754d9-285">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="754d9-286">`Excluded`: no incluir nunca metadatos para el miembro.</span><span class="sxs-lookup"><span data-stu-id="754d9-286">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="754d9-287">`Included`: habilitar la directiva, si el tipo primario está presente en la salida.</span><span class="sxs-lookup"><span data-stu-id="754d9-287">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="754d9-288">`Required`: exige que la cadena de herramientas mantenga este miembro incluso si no parece usado, y habilitar una directiva para él.</span><span class="sxs-lookup"><span data-stu-id="754d9-288">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="754d9-289">Semántica de archivos de directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="754d9-289">Runtime directives file semantics</span></span>

<span data-ttu-id="754d9-290">La directiva puede definirse simultáneamente para elementos de nivel superior y de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="754d9-290">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="754d9-291">Por ejemplo, puede definirse la directiva de un ensamblado y de algunos de los tipos contenidos en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="754d9-291">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="754d9-292">Si un elemento determinado de nivel inferior no está representado, hereda la directiva de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="754d9-292">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="754d9-293">Por ejemplo, si un elemento `Assembly` está presente pero el elemento `Type` no, la directiva especificada en el elemento `Assembly` se aplica a cada tipo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="754d9-293">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="754d9-294">Varios elementos también pueden aplicar una directiva al mismo elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="754d9-294">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="754d9-295">Por ejemplo, es posible que distintos elementos [Assembly](assembly-element-net-native.md) definan el mismo elemento de directiva para el mismo ensamblado de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="754d9-295">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="754d9-296">Las siguientes secciones explican cómo se resuelve la directiva para un tipo concreto en esos casos.</span><span class="sxs-lookup"><span data-stu-id="754d9-296">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="754d9-297">Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) de un tipo o método genérico aplica su directiva a todas las creaciones de instancias que no tienen su propia directiva.</span><span class="sxs-lookup"><span data-stu-id="754d9-297">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="754d9-298">Por ejemplo, un elemento `Type` que especifica la directiva de <xref:System.Collections.Generic.List%601> se aplica a todas las instancias construidas de ese tipo genérico, a menos que un elemento `List<Int32>` las invalide para un determinado tipo genérico construido (como un `TypeInstantiation`).</span><span class="sxs-lookup"><span data-stu-id="754d9-298">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="754d9-299">De lo contrario, los elementos definen la directiva para el elemento de programa denominado.</span><span class="sxs-lookup"><span data-stu-id="754d9-299">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="754d9-300">Cuando un elemento es ambiguo, el motor busca coincidencias y, si encuentra a una coincidencia exacta, la utiliza.</span><span class="sxs-lookup"><span data-stu-id="754d9-300">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="754d9-301">Si encuentra a varias coincidencias, habrá una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="754d9-301">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="754d9-302">Si dos directivas directiva se aplican al mismo elemento de programa</span><span class="sxs-lookup"><span data-stu-id="754d9-302">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="754d9-303">Si dos elementos de diferentes archivos de directivas de tiempo de ejecución intentan establecer el mismo tipo de directiva para el mismo elemento de programa (por ejemplo, un ensamblado o tipo) en valores diferentes, el conflicto se resuelve como sigue:</span><span class="sxs-lookup"><span data-stu-id="754d9-303">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="754d9-304">Si el elemento `Excluded` está presente, tiene precedencia.</span><span class="sxs-lookup"><span data-stu-id="754d9-304">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="754d9-305">`Required` tiene precedencia sobre no `Required`.</span><span class="sxs-lookup"><span data-stu-id="754d9-305">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="754d9-306">`All` tiene precedencia sobre `PublicAndInternal`, que tiene precedencia sobre `Public`.</span><span class="sxs-lookup"><span data-stu-id="754d9-306">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="754d9-307">Cualquier valor explícito tiene precedencia sobre `Auto`.</span><span class="sxs-lookup"><span data-stu-id="754d9-307">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="754d9-308">Por ejemplo, si un único proyecto incluye los dos archivos de directivas de tiempo de ejecución siguientes, la directiva de serialización para DataClasses.dll se establece tanto en `Required Public` como en `All`.</span><span class="sxs-lookup"><span data-stu-id="754d9-308">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="754d9-309">En este caso, la directiva de serialización se puede resolver como `Required All`.</span><span class="sxs-lookup"><span data-stu-id="754d9-309">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="754d9-310">Sin embargo, si dos directivas de un único archivo de directivas de tiempo de ejecución intenta establecer el mismo tipo de directiva para el mismo elemento de programa, la herramienta de definición de esquema XML muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="754d9-310">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="754d9-311">Si elementos primarios y secundarios aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="754d9-311">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="754d9-312">Los elementos secundarios invalidan a sus elementos primarios, incluido el valor `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="754d9-312">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="754d9-313">La invalidación es la razón principal por la que desearía especificar `Auto`.</span><span class="sxs-lookup"><span data-stu-id="754d9-313">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="754d9-314">En el siguiente ejemplo, el valor de directiva de serialización para todo lo contenido en `DataClasses` que no está en `DataClasses.ViewModels` sería `Required Public`, y todo lo que está tanto en `DataClasses` como en `DataClasses.ViewModels` sería `All`.</span><span class="sxs-lookup"><span data-stu-id="754d9-314">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="754d9-315">Si los genéricos abiertos y elementos con instancia aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="754d9-315">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="754d9-316">En el siguiente ejemplo, la directiva `Dictionary<int,int>` se asigna a `Browse` solo si el motor tiene otra razón para darle otorgarle la directiva `Browse` (que de lo contrario sería el comportamiento predeterminado); todos los miembros del resto de creaciones de instancias de <xref:System.Collections.Generic.Dictionary%602> se podrán examinar.</span><span class="sxs-lookup"><span data-stu-id="754d9-316">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="754d9-317">Cómo se infiere la directiva</span><span class="sxs-lookup"><span data-stu-id="754d9-317">How policy is inferred</span></span>

<span data-ttu-id="754d9-318">Cada tipo de directiva tiene un conjunto diferente de reglas que determinan cómo la presencia de ese tipo de directiva afecta a otras construcciones.</span><span class="sxs-lookup"><span data-stu-id="754d9-318">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="754d9-319">El efecto de la directiva Browse</span><span class="sxs-lookup"><span data-stu-id="754d9-319">The effect of Browse policy</span></span>

<span data-ttu-id="754d9-320">Aplicar la directiva `Browse` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-320">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-321">El tipo base del tipo que está marcado con directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-321">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-322">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-322">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-323">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-323">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-324">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-324">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-325">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-325">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-326">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-326">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-327">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-327">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="754d9-328">Aplicar la directiva `Browse` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-328">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-329">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-329">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-330">El tipo devuelto del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-330">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-331">El tipo contenedor del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-331">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-332">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-332">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-333">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-333">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-334">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-334">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-335">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-335">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="754d9-336">Aplicar la directiva `Browse` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-336">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-337">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-337">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-338">El tipo del campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-338">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-339">El tipo al que pertenece el campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-339">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="754d9-340">Efecto de la directiva Dynamic</span><span class="sxs-lookup"><span data-stu-id="754d9-340">The effect of Dynamic policy</span></span>

<span data-ttu-id="754d9-341">Aplicar la directiva `Dynamic` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-341">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-342">El tipo base del tipo que está marcado con directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-342">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-343">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-343">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-344">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-344">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-345">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-345">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-346">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-346">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-347">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-347">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-348">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-348">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="754d9-349">Aplicar la directiva `Dynamic` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-349">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-350">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-350">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-351">El tipo devuelto del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-351">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-352">El tipo contenedor del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-352">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-353">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-353">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-354">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-354">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-355">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-355">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-356">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-356">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-357">`MethodInfo.Invoke` puede invocar al método y la creación de delegados se hace posible mediante <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="754d9-357">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="754d9-358">Aplicar la directiva `Dynamic` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-358">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-359">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-359">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-360">El tipo del campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-360">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-361">El tipo al que pertenece el campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-361">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="754d9-362">Efecto de la directiva Activation</span><span class="sxs-lookup"><span data-stu-id="754d9-362">The effect of Activation policy</span></span>

<span data-ttu-id="754d9-363">Aplicar la directiva Activation a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-363">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-364">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-364">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-365">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-365">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-366">Los constructores del tipo se marcan con la directiva `Activation`.</span><span class="sxs-lookup"><span data-stu-id="754d9-366">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="754d9-367">Aplicar la directiva `Activation` a un método implica el siguiente cambio de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-367">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="754d9-368">El constructor puede invocarse mediante los métodos <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> y <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="754d9-368">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="754d9-369">En cuanto a los métodos, la directiva `Activation` solo afecta a constructores.</span><span class="sxs-lookup"><span data-stu-id="754d9-369">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="754d9-370">Aplicar la directiva `Activation` a un campo no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="754d9-370">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="754d9-371">Efecto de la directiva Serialize</span><span class="sxs-lookup"><span data-stu-id="754d9-371">The effect of Serialize policy</span></span>

<span data-ttu-id="754d9-372">La directiva `Serialize` permite el uso de serializadores comunes basados en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="754d9-372">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="754d9-373">Sin embargo, dado que Microsoft no conoce los patrones de acceso reflejo exacto de los serializadores que no son de Microsoft, esta directiva puede no ser totalmente efectiva.</span><span class="sxs-lookup"><span data-stu-id="754d9-373">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="754d9-374">Aplicar la directiva `Serialize` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-374">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-375">El tipo base del tipo que está marcado con directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-375">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-376">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="754d9-376">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="754d9-377">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="754d9-377">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="754d9-378">Si el tipo es una enumeración, una matriz del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-378">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-379">Si el tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-379">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-380">Si el tipo es <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, entonces `T[]` y <xref:System.Collections.Generic.List%601> se marcan con la directiva `Serialize`. Sin embargo, ningún miembro del tipo de interfaz se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-380">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-381">Si el tipo es <xref:System.Collections.Generic.List%601>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-381">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-382">Si el tipo es <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-382">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="754d9-383">En cambio, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-383">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-384">Si el tipo es <xref:System.Collections.Generic.Dictionary%602>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-384">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-385">Si el tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` y `TValue` se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-385">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-386">Todos los constructores, todos los descriptores de acceso de propiedad y todos los campos se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-386">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="754d9-387">Aplicar la directiva `Serialize` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-387">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-388">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-388">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-389">El tipo devuelto del método se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-389">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="754d9-390">Aplicar la directiva `Serialize` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="754d9-390">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="754d9-391">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-391">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="754d9-392">El tipo del campo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="754d9-392">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="754d9-393">Efecto de las directivas XmlSerializer, DataContractSerializer y DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="754d9-393">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="754d9-394">A diferencia de la `Serialize` Directiva, que está destinada a los serializadores basados en reflexión, las <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractSerializer> directivas, y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> se usan para habilitar un conjunto de serializadores conocidos por la cadena de herramientas de .net Native.</span><span class="sxs-lookup"><span data-stu-id="754d9-394">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="754d9-395">Estos serializadores no se implementan mediante reflexión, pero el conjunto de tipos que se pueden serializar en tiempo de ejecución se determina de manera similar a los tipos que admiten reflexión.</span><span class="sxs-lookup"><span data-stu-id="754d9-395">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="754d9-396">Aplicar una de estas directivas a un tipo permite la serialización del tipo con el serializador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="754d9-396">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="754d9-397">Además, los tipos que el motor de serialización puede determinar de forma estática que necesitan serialización también se podrán serializar.</span><span class="sxs-lookup"><span data-stu-id="754d9-397">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="754d9-398">Estas directivas no tienen efecto sobre los campos o métodos.</span><span class="sxs-lookup"><span data-stu-id="754d9-398">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="754d9-399">Para más información, vea la sección "Diferencias en los serializadores" en [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-399">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="754d9-400">Vea también</span><span class="sxs-lookup"><span data-stu-id="754d9-400">See also</span></span>

- [<span data-ttu-id="754d9-401">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="754d9-401">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="754d9-402">Reflexión y .NET Native</span><span class="sxs-lookup"><span data-stu-id="754d9-402">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

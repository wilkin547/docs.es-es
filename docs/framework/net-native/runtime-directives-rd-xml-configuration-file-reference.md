---
title: Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738410"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="445d3-102">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="445d3-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="445d3-103">Un archivo de directivas de tiempo de ejecución (.rd.xml) es un archivo de configuración XML que especifica si los elementos de programa designados están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="445d3-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="445d3-104">A continuación se muestra un ejemplo de un archivo de directivas de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="445d3-104">Here’s an example of a runtime directives file:</span></span>

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

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="445d3-105">Estructura de un archivo de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="445d3-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="445d3-106">El archivo de directivas de tiempo de ejecución utiliza el espacio de nombres `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="445d3-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="445d3-107">El elemento raíz es [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="445d3-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="445d3-108">Puede contener cero o más elementos [Library](library-element-net-native.md) y cero o un elemento [Application](application-element-net-native.md), como se muestra en la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="445d3-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="445d3-109">Los atributos del elemento [Application](application-element-net-native.md) pueden definir directivas de reflexión en tiempo de ejecución para toda la aplicación, o puede actuar como contenedor de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="445d3-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="445d3-110">El elemento [Library](library-element-net-native.md), por otro lado, es simplemente un contenedor.</span><span class="sxs-lookup"><span data-stu-id="445d3-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="445d3-111">Los elementos secundarios de los elementos [Application](application-element-net-native.md) y [Library](library-element-net-native.md) definen los tipos, métodos, campos, propiedades y eventos que están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="445d3-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="445d3-112">Para obtener información de referencia, seleccione los elementos de la siguiente estructura o vea [Runtime Directive Elements](runtime-directive-elements.md) (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="445d3-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="445d3-113">En la siguiente jerarquía, los puntos suspensivos marcan una estructura recursiva.</span><span class="sxs-lookup"><span data-stu-id="445d3-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="445d3-114">La información entre paréntesis indica si el elemento es obligatorio u opcional y, si se utiliza, el número de instancias permitidas (una o varias).</span><span class="sxs-lookup"><span data-stu-id="445d3-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

- <span data-ttu-id="445d3-115">[Directives](directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-115">[Directives](directives-element-net-native.md) [1:1]</span></span>
  - <span data-ttu-id="445d3-116">[Application](application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-116">[Application](application-element-net-native.md) [0:1]</span></span>
    - <span data-ttu-id="445d3-117">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-117">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-118">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-118">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-119">.</span><span class="sxs-lookup"><span data-stu-id="445d3-119">.</span></span> <span data-ttu-id="445d3-120">.</span><span class="sxs-lookup"><span data-stu-id="445d3-120">.</span></span>
      - <span data-ttu-id="445d3-121">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-121">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-122">.</span><span class="sxs-lookup"><span data-stu-id="445d3-122">.</span></span> <span data-ttu-id="445d3-123">.</span><span class="sxs-lookup"><span data-stu-id="445d3-123">.</span></span>
      - <span data-ttu-id="445d3-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-125">.</span><span class="sxs-lookup"><span data-stu-id="445d3-125">.</span></span> <span data-ttu-id="445d3-126">.</span><span class="sxs-lookup"><span data-stu-id="445d3-126">.</span></span>
    - <span data-ttu-id="445d3-127">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-127">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-128">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-128">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-129">.</span><span class="sxs-lookup"><span data-stu-id="445d3-129">.</span></span> <span data-ttu-id="445d3-130">.</span><span class="sxs-lookup"><span data-stu-id="445d3-130">.</span></span>
      - <span data-ttu-id="445d3-131">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-131">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-132">.</span><span class="sxs-lookup"><span data-stu-id="445d3-132">.</span></span> <span data-ttu-id="445d3-133">.</span><span class="sxs-lookup"><span data-stu-id="445d3-133">.</span></span>
      - <span data-ttu-id="445d3-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-135">.</span><span class="sxs-lookup"><span data-stu-id="445d3-135">.</span></span> <span data-ttu-id="445d3-136">.</span><span class="sxs-lookup"><span data-stu-id="445d3-136">.</span></span>
    - <span data-ttu-id="445d3-137">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-137">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-138">[Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-138">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="445d3-139">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-139">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-140">.</span><span class="sxs-lookup"><span data-stu-id="445d3-140">.</span></span> <span data-ttu-id="445d3-141">.</span><span class="sxs-lookup"><span data-stu-id="445d3-141">.</span></span>
      - <span data-ttu-id="445d3-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-143">.</span><span class="sxs-lookup"><span data-stu-id="445d3-143">.</span></span> <span data-ttu-id="445d3-144">.</span><span class="sxs-lookup"><span data-stu-id="445d3-144">.</span></span>
      - <span data-ttu-id="445d3-145">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-145">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="445d3-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-147">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-147">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-148">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-148">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="445d3-152">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-152">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-153">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-153">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-154">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-154">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="445d3-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="445d3-156">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-156">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-157">.</span><span class="sxs-lookup"><span data-stu-id="445d3-157">.</span></span> <span data-ttu-id="445d3-158">.</span><span class="sxs-lookup"><span data-stu-id="445d3-158">.</span></span>
      - <span data-ttu-id="445d3-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-160">.</span><span class="sxs-lookup"><span data-stu-id="445d3-160">.</span></span> <span data-ttu-id="445d3-161">.</span><span class="sxs-lookup"><span data-stu-id="445d3-161">.</span></span>
      - <span data-ttu-id="445d3-162">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-162">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-163">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-163">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="445d3-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="445d3-167">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-167">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-168">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-168">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-169">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-169">[Event](event-element-net-native.md) [0:M]</span></span>
  - <span data-ttu-id="445d3-170">[Library](library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-170">[Library](library-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="445d3-171">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-171">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-172">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-172">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-173">.</span><span class="sxs-lookup"><span data-stu-id="445d3-173">.</span></span> <span data-ttu-id="445d3-174">.</span><span class="sxs-lookup"><span data-stu-id="445d3-174">.</span></span>
      - <span data-ttu-id="445d3-175">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-175">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-176">.</span><span class="sxs-lookup"><span data-stu-id="445d3-176">.</span></span> <span data-ttu-id="445d3-177">.</span><span class="sxs-lookup"><span data-stu-id="445d3-177">.</span></span>
      - <span data-ttu-id="445d3-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-179">.</span><span class="sxs-lookup"><span data-stu-id="445d3-179">.</span></span> <span data-ttu-id="445d3-180">.</span><span class="sxs-lookup"><span data-stu-id="445d3-180">.</span></span>
    - <span data-ttu-id="445d3-181">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-181">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-182">[Espacio de nombres](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-182">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-183">.</span><span class="sxs-lookup"><span data-stu-id="445d3-183">.</span></span> <span data-ttu-id="445d3-184">.</span><span class="sxs-lookup"><span data-stu-id="445d3-184">.</span></span>
      - <span data-ttu-id="445d3-185">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-185">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-186">.</span><span class="sxs-lookup"><span data-stu-id="445d3-186">.</span></span> <span data-ttu-id="445d3-187">.</span><span class="sxs-lookup"><span data-stu-id="445d3-187">.</span></span>
      - <span data-ttu-id="445d3-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-189">.</span><span class="sxs-lookup"><span data-stu-id="445d3-189">.</span></span> <span data-ttu-id="445d3-190">.</span><span class="sxs-lookup"><span data-stu-id="445d3-190">.</span></span>
    - <span data-ttu-id="445d3-191">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-191">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-192">[Subtypes](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-192">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="445d3-193">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-193">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-194">.</span><span class="sxs-lookup"><span data-stu-id="445d3-194">.</span></span> <span data-ttu-id="445d3-195">.</span><span class="sxs-lookup"><span data-stu-id="445d3-195">.</span></span>
      - <span data-ttu-id="445d3-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-197">.</span><span class="sxs-lookup"><span data-stu-id="445d3-197">.</span></span> <span data-ttu-id="445d3-198">.</span><span class="sxs-lookup"><span data-stu-id="445d3-198">.</span></span>
      - <span data-ttu-id="445d3-199">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1]</span><span class="sxs-lookup"><span data-stu-id="445d3-199">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="445d3-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-201">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-201">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="445d3-203">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-203">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-204">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-204">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-205">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-205">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="445d3-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="445d3-207">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-207">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="445d3-208">.</span><span class="sxs-lookup"><span data-stu-id="445d3-208">.</span></span> <span data-ttu-id="445d3-209">.</span><span class="sxs-lookup"><span data-stu-id="445d3-209">.</span></span>
      - <span data-ttu-id="445d3-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="445d3-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="445d3-211">.</span><span class="sxs-lookup"><span data-stu-id="445d3-211">.</span></span> <span data-ttu-id="445d3-212">.</span><span class="sxs-lookup"><span data-stu-id="445d3-212">.</span></span>
      - <span data-ttu-id="445d3-213">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-213">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="445d3-215">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-215">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-216">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-216">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="445d3-217">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="445d3-217">[Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="445d3-218">El elemento [Application](application-element-net-native.md) no puede tener atributos o puede tener los atributos de directiva tratados en la [sección sobre política y directivas de tiempo de ejecución](#Directives).</span><span class="sxs-lookup"><span data-stu-id="445d3-218">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="445d3-219">Un elemento [Library](library-element-net-native.md) tiene un solo atributo, `Name`, que especifica el nombre de una biblioteca o ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="445d3-219">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="445d3-220">Por ejemplo, el siguiente elemento [Library](library-element-net-native.md) se aplica a un ensamblado denominado Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="445d3-220">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

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

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="445d3-221">Política y directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="445d3-221">Runtime directives and policy</span></span>

<span data-ttu-id="445d3-222">El elemento [Application](application-element-net-native.md) y los elementos secundarios de los elementos [Library](library-element-net-native.md) y [Application](application-element-net-native.md) expresan directiva; es decir, definen la forma en que una aplicación puede aplicar reflexión a un elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="445d3-222">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="445d3-223">El tipo de la directiva se define mediante un atributo del elemento (por ejemplo, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="445d3-223">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="445d3-224">El valor de la directiva se define mediante el valor del atributo (por ejemplo, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="445d3-224">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="445d3-225">Cualquier directiva especificada por un atributo de un elemento se aplica a todos los elementos secundarios que no especifican ningún valor para esa directiva.</span><span class="sxs-lookup"><span data-stu-id="445d3-225">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="445d3-226">Por ejemplo, si una directiva se especifica mediante un elemento [Type](type-element-net-native.md), esa directiva se aplica a todos los tipos y miembros contenidos para los que no se especifica explícitamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="445d3-226">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="445d3-227">La directiva que puede expresarse mediante los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) difiere de la que puede expresarse para miembros individuales (mediante los elementos [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) y [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="445d3-227">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="445d3-228">Especificar la directiva para ensamblados, espacios de nombres y tipos</span><span class="sxs-lookup"><span data-stu-id="445d3-228">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="445d3-229">Los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="445d3-229">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="445d3-230">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="445d3-230">`Activate`.</span></span> <span data-ttu-id="445d3-231">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de las instancias.</span><span class="sxs-lookup"><span data-stu-id="445d3-231">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="445d3-232">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-232">`Browse`.</span></span> <span data-ttu-id="445d3-233">Controla la consulta de información sobre elementos del programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="445d3-233">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="445d3-234">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-234">`Dynamic`.</span></span> <span data-ttu-id="445d3-235">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="445d3-235">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="445d3-236">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-236">`Serialize`.</span></span> <span data-ttu-id="445d3-237">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades, para permitir que bibliotecas de terceros (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="445d3-237">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="445d3-238">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="445d3-238">`DataContractSerializer`.</span></span> <span data-ttu-id="445d3-239">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="445d3-239">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="445d3-240">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="445d3-240">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="445d3-241">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="445d3-241">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="445d3-242">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="445d3-242">`XmlSerializer`.</span></span> <span data-ttu-id="445d3-243">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="445d3-243">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="445d3-244">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="445d3-244">`MarshalObject`.</span></span> <span data-ttu-id="445d3-245">Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="445d3-245">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="445d3-246">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="445d3-246">`MarshalDelegate`.</span></span> <span data-ttu-id="445d3-247">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="445d3-247">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="445d3-248">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="445d3-248">`MarshalStructure` .</span></span> <span data-ttu-id="445d3-249">Controla la directiva para calcular referencias de estructuras a código nativo.</span><span class="sxs-lookup"><span data-stu-id="445d3-249">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="445d3-250">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="445d3-250">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="445d3-251">`All`.</span><span class="sxs-lookup"><span data-stu-id="445d3-251">`All`.</span></span> <span data-ttu-id="445d3-252">Habilita la directiva para todos los tipos y miembros que no se eliminan con la cadena de herramientas.</span><span class="sxs-lookup"><span data-stu-id="445d3-252">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="445d3-253">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="445d3-253">`Auto`.</span></span> <span data-ttu-id="445d3-254">Usa el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="445d3-254">Use the default behavior.</span></span> <span data-ttu-id="445d3-255">(No especificar una directiva es equivalente a establecer esa directiva en `Auto`, a menos que se invalide la directiva, por ejemplo, por un elemento primario).</span><span class="sxs-lookup"><span data-stu-id="445d3-255">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="445d3-256">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="445d3-256">`Excluded`.</span></span> <span data-ttu-id="445d3-257">Deshabilita la directiva para el elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="445d3-257">Disable the policy for the program element.</span></span>

- <span data-ttu-id="445d3-258">`Public`.</span><span class="sxs-lookup"><span data-stu-id="445d3-258">`Public`.</span></span> <span data-ttu-id="445d3-259">Habilita la directiva para tipos o miembros públicos a menos que la cadena de herramientas determine que el miembro es innecesario y, por tanto, lo quita.</span><span class="sxs-lookup"><span data-stu-id="445d3-259">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="445d3-260">(En este último caso, debe utilizar `Required Public` para asegurarse de que el miembro se conserva y tiene capacidades de reflexión).</span><span class="sxs-lookup"><span data-stu-id="445d3-260">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="445d3-261">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="445d3-261">`PublicAndInternal`.</span></span> <span data-ttu-id="445d3-262">Habilita la directiva para tipos o miembros públicos e internos si la cadena de herramientas no los quita.</span><span class="sxs-lookup"><span data-stu-id="445d3-262">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="445d3-263">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="445d3-263">`Required Public`.</span></span> <span data-ttu-id="445d3-264">Exige que la cadena de herramientas mantenga los tipos y miembros públicos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="445d3-264">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="445d3-265">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="445d3-265">`Required PublicAndInternal`.</span></span> <span data-ttu-id="445d3-266">Exige que la cadena de herramientas mantenga los tipos y miembros públicos e internos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="445d3-266">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="445d3-267">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="445d3-267">`Required All`.</span></span> <span data-ttu-id="445d3-268">Exige que la cadena de herramientas mantenga todos los tipos y miembros tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="445d3-268">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="445d3-269">Por ejemplo, el siguiente archivo de directivas de tiempo de ejecución define una directiva para todos los tipos y miembros del ensamblado DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="445d3-269">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="445d3-270">Permite reflexión para la serialización de todas las propiedades públicas, permite buscar todos los tipos y miembros de tipo, permite la activación para todos los tipos (debido al atributo `Dynamic`) y permite la reflexión para todos los tipos y miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="445d3-270">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

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

### <a name="specifying-policy-for-members"></a><span data-ttu-id="445d3-271">Especificar la directiva para los miembros</span><span class="sxs-lookup"><span data-stu-id="445d3-271">Specifying policy for members</span></span>

<span data-ttu-id="445d3-272">Los elementos [Property](property-element-net-native.md) y [Field](field-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="445d3-272">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="445d3-273">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="445d3-273">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="445d3-274">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="445d3-274">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="445d3-275">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="445d3-275">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="445d3-276">`Serialize`: controla el acceso en tiempo de ejecución al miembro para permitir que las bibliotecas (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="445d3-276">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="445d3-277">Esta directiva puede aplicarse a propiedades, campos y constructores.</span><span class="sxs-lookup"><span data-stu-id="445d3-277">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="445d3-278">Los elementos [Method](method-element-net-native.md) y [Event](event-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="445d3-278">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="445d3-279">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="445d3-279">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="445d3-280">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="445d3-280">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="445d3-281">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="445d3-281">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="445d3-282">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="445d3-282">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="445d3-283">`Auto`: usar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="445d3-283">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="445d3-284">(No especificar una política es equivalente a establecer esa directiva en `Auto`, a menos que algo la invalide).</span><span class="sxs-lookup"><span data-stu-id="445d3-284">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="445d3-285">`Excluded`: no incluir nunca metadatos para el miembro.</span><span class="sxs-lookup"><span data-stu-id="445d3-285">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="445d3-286">`Included`: habilitar la directiva, si el tipo primario está presente en la salida.</span><span class="sxs-lookup"><span data-stu-id="445d3-286">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="445d3-287">`Required`: exige que la cadena de herramientas mantenga este miembro incluso si no parece usado, y habilitar una directiva para él.</span><span class="sxs-lookup"><span data-stu-id="445d3-287">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="445d3-288">Semántica de archivos de directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="445d3-288">Runtime directives file semantics</span></span>

<span data-ttu-id="445d3-289">La directiva puede definirse simultáneamente para elementos de nivel superior y de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="445d3-289">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="445d3-290">Por ejemplo, puede definirse la directiva de un ensamblado y de algunos de los tipos contenidos en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="445d3-290">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="445d3-291">Si un elemento determinado de nivel inferior no está representado, hereda la directiva de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="445d3-291">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="445d3-292">Por ejemplo, si un elemento `Assembly` está presente pero el elemento `Type` no, la directiva especificada en el elemento `Assembly` se aplica a cada tipo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="445d3-292">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="445d3-293">Varios elementos también pueden aplicar una directiva al mismo elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="445d3-293">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="445d3-294">Por ejemplo, es posible que distintos elementos [Assembly](assembly-element-net-native.md) definan el mismo elemento de directiva para el mismo ensamblado de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="445d3-294">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="445d3-295">Las siguientes secciones explican cómo se resuelve la directiva para un tipo concreto en esos casos.</span><span class="sxs-lookup"><span data-stu-id="445d3-295">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="445d3-296">Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) de un tipo o método genérico aplica su directiva a todas las creaciones de instancias que no tienen su propia directiva.</span><span class="sxs-lookup"><span data-stu-id="445d3-296">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="445d3-297">Por ejemplo, un elemento `Type` que especifica la directiva de <xref:System.Collections.Generic.List%601> se aplica a todas las instancias construidas de ese tipo genérico, a menos que un elemento `List<Int32>` las invalide para un determinado tipo genérico construido (como un `TypeInstantiation`).</span><span class="sxs-lookup"><span data-stu-id="445d3-297">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="445d3-298">De lo contrario, los elementos definen la directiva para el elemento de programa denominado.</span><span class="sxs-lookup"><span data-stu-id="445d3-298">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="445d3-299">Cuando un elemento es ambiguo, el motor busca coincidencias y, si encuentra a una coincidencia exacta, la utiliza.</span><span class="sxs-lookup"><span data-stu-id="445d3-299">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="445d3-300">Si encuentra a varias coincidencias, habrá una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="445d3-300">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="445d3-301">Si dos directivas directiva se aplican al mismo elemento de programa</span><span class="sxs-lookup"><span data-stu-id="445d3-301">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="445d3-302">Si dos elementos de diferentes archivos de directivas de tiempo de ejecución intentan establecer el mismo tipo de directiva para el mismo elemento de programa (por ejemplo, un ensamblado o tipo) en valores diferentes, el conflicto se resuelve como sigue:</span><span class="sxs-lookup"><span data-stu-id="445d3-302">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="445d3-303">Si el elemento `Excluded` está presente, tiene precedencia.</span><span class="sxs-lookup"><span data-stu-id="445d3-303">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="445d3-304">`Required` tiene precedencia sobre no `Required`.</span><span class="sxs-lookup"><span data-stu-id="445d3-304">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="445d3-305">`All` tiene precedencia sobre `PublicAndInternal`, que tiene precedencia sobre `Public`.</span><span class="sxs-lookup"><span data-stu-id="445d3-305">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="445d3-306">Cualquier valor explícito tiene precedencia sobre `Auto`.</span><span class="sxs-lookup"><span data-stu-id="445d3-306">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="445d3-307">Por ejemplo, si un único proyecto incluye los dos archivos de directivas de tiempo de ejecución siguientes, la directiva de serialización para DataClasses.dll se establece tanto en `Required Public` como en `All`.</span><span class="sxs-lookup"><span data-stu-id="445d3-307">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="445d3-308">En este caso, la directiva de serialización se puede resolver como `Required All`.</span><span class="sxs-lookup"><span data-stu-id="445d3-308">In this case, the serialization policy would be resolved as `Required All`.</span></span>

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

<span data-ttu-id="445d3-309">Sin embargo, si dos directivas de un único archivo de directivas de tiempo de ejecución intenta establecer el mismo tipo de directiva para el mismo elemento de programa, la herramienta de definición de esquema XML muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="445d3-309">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="445d3-310">Si elementos primarios y secundarios aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="445d3-310">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="445d3-311">Los elementos secundarios invalidan a sus elementos primarios, incluido el valor `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="445d3-311">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="445d3-312">La invalidación es la razón principal por la que desearía especificar `Auto`.</span><span class="sxs-lookup"><span data-stu-id="445d3-312">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="445d3-313">En el siguiente ejemplo, el valor de directiva de serialización para todo lo contenido en `DataClasses` que no está en `DataClasses.ViewModels` sería `Required Public`, y todo lo que está tanto en `DataClasses` como en `DataClasses.ViewModels` sería `All`.</span><span class="sxs-lookup"><span data-stu-id="445d3-313">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

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

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="445d3-314">Si los genéricos abiertos y elementos con instancia aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="445d3-314">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="445d3-315">En el siguiente ejemplo, la directiva `Dictionary<int,int>` se asigna a `Browse` solo si el motor tiene otra razón para darle otorgarle la directiva `Browse` (que de lo contrario sería el comportamiento predeterminado); todos los miembros del resto de creaciones de instancias de <xref:System.Collections.Generic.Dictionary%602> se podrán examinar.</span><span class="sxs-lookup"><span data-stu-id="445d3-315">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

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

### <a name="how-policy-is-inferred"></a><span data-ttu-id="445d3-316">Cómo se infiere la directiva</span><span class="sxs-lookup"><span data-stu-id="445d3-316">How policy is inferred</span></span>

<span data-ttu-id="445d3-317">Cada tipo de directiva tiene un conjunto diferente de reglas que determinan cómo la presencia de ese tipo de directiva afecta a otras construcciones.</span><span class="sxs-lookup"><span data-stu-id="445d3-317">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="445d3-318">El efecto de la directiva Browse</span><span class="sxs-lookup"><span data-stu-id="445d3-318">The effect of Browse policy</span></span>

<span data-ttu-id="445d3-319">Aplicar la directiva `Browse` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-319">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-320">El tipo base del tipo que está marcado con directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-320">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-321">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-322">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-322">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-323">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-323">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-324">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-324">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-325">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-325">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-326">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-326">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="445d3-327">Aplicar la directiva `Browse` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-327">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-328">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-328">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-329">El tipo devuelto del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-329">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-330">El tipo contenedor del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-330">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-331">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-331">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-332">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-332">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-333">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-333">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-334">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-334">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="445d3-335">Aplicar la directiva `Browse` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-335">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-336">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-336">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-337">El tipo del campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-337">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-338">El tipo al que pertenece el campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-338">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="445d3-339">Efecto de la directiva Dynamic</span><span class="sxs-lookup"><span data-stu-id="445d3-339">The effect of Dynamic policy</span></span>

<span data-ttu-id="445d3-340">Aplicar la directiva `Dynamic` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-340">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-341">El tipo base del tipo que está marcado con directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-341">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-342">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-342">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-343">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-343">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-344">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-344">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-345">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-345">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-346">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-346">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-347">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-347">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="445d3-348">Aplicar la directiva `Dynamic` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-348">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-349">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-349">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-350">El tipo devuelto del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-350">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-351">El tipo contenedor del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-351">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-352">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-352">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-353">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-353">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-354">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-354">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-355">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-355">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-356">`MethodInfo.Invoke` puede invocar al método y la creación de delegados se hace posible mediante <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="445d3-356">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="445d3-357">Aplicar la directiva `Dynamic` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-357">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-358">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-358">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-359">El tipo del campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-359">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-360">El tipo al que pertenece el campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-360">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="445d3-361">Efecto de la directiva Activation</span><span class="sxs-lookup"><span data-stu-id="445d3-361">The effect of Activation policy</span></span>

<span data-ttu-id="445d3-362">Aplicar la directiva Activation a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-362">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-363">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-363">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-364">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-364">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-365">Los constructores del tipo se marcan con la directiva `Activation`.</span><span class="sxs-lookup"><span data-stu-id="445d3-365">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="445d3-366">Aplicar la directiva `Activation` a un método implica el siguiente cambio de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-366">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="445d3-367">El constructor puede invocarse mediante los métodos <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> y <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="445d3-367">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="445d3-368">En cuanto a los métodos, la directiva `Activation` solo afecta a constructores.</span><span class="sxs-lookup"><span data-stu-id="445d3-368">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="445d3-369">Aplicar la directiva `Activation` a un campo no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="445d3-369">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="445d3-370">Efecto de la directiva Serialize</span><span class="sxs-lookup"><span data-stu-id="445d3-370">The effect of Serialize policy</span></span>

<span data-ttu-id="445d3-371">La directiva `Serialize` permite el uso de serializadores comunes basados en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="445d3-371">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="445d3-372">Sin embargo, dado que Microsoft no conoce los patrones de acceso reflejo exacto de los serializadores que no son de Microsoft, esta directiva puede no ser totalmente efectiva.</span><span class="sxs-lookup"><span data-stu-id="445d3-372">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="445d3-373">Aplicar la directiva `Serialize` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-373">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-374">El tipo base del tipo que está marcado con directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-374">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-375">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="445d3-375">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="445d3-376">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="445d3-376">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="445d3-377">Si el tipo es una enumeración, una matriz del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-377">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-378">Si el tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-378">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-379">Si el tipo es <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, entonces `T[]` y <xref:System.Collections.Generic.List%601> se marcan con la directiva `Serialize`. Sin embargo, ningún miembro del tipo de interfaz se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-379">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-380">Si el tipo es <xref:System.Collections.Generic.List%601>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-380">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-381">Si el tipo es <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-381">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="445d3-382">En cambio, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-382">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-383">Si el tipo es <xref:System.Collections.Generic.Dictionary%602>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-383">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-384">Si el tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` y `TValue` se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-384">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-385">Todos los constructores, todos los descriptores de acceso de propiedad y todos los campos se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-385">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="445d3-386">Aplicar la directiva `Serialize` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-386">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-387">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-387">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-388">El tipo devuelto del método se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-388">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="445d3-389">Aplicar la directiva `Serialize` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="445d3-389">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="445d3-390">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-390">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="445d3-391">El tipo del campo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="445d3-391">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="445d3-392">Efecto de las directivas XmlSerializer, DataContractSerializer y DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="445d3-392">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="445d3-393">A diferencia de la Directiva de `Serialize`, que está destinada a los serializadores basados en reflexión, las directivas <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> se utilizan para habilitar un conjunto de serializadores conocidos para la cadena de herramientas de .NET Native.</span><span class="sxs-lookup"><span data-stu-id="445d3-393">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="445d3-394">Estos serializadores no se implementan mediante reflexión, pero el conjunto de tipos que se pueden serializar en tiempo de ejecución se determina de manera similar a los tipos que admiten reflexión.</span><span class="sxs-lookup"><span data-stu-id="445d3-394">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="445d3-395">Aplicar una de estas directivas a un tipo permite la serialización del tipo con el serializador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="445d3-395">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="445d3-396">Además, los tipos que el motor de serialización puede determinar de forma estática que necesitan serialización también se podrán serializar.</span><span class="sxs-lookup"><span data-stu-id="445d3-396">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="445d3-397">Estas directivas no tienen efecto sobre los campos o métodos.</span><span class="sxs-lookup"><span data-stu-id="445d3-397">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="445d3-398">Para más información, vea la sección "Diferencias en los serializadores" en [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="445d3-398">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="445d3-399">Consulte también</span><span class="sxs-lookup"><span data-stu-id="445d3-399">See also</span></span>

- [<span data-ttu-id="445d3-400">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="445d3-400">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="445d3-401">Reflexión y .NET Native</span><span class="sxs-lookup"><span data-stu-id="445d3-401">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

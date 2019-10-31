---
title: Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: f4c51dc269775d14d395cb464b3787cc987e086d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128129"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="134c0-102">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="134c0-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="134c0-103">Un archivo de directivas de tiempo de ejecución (.rd.xml) es un archivo de configuración XML que especifica si los elementos de programa designados están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="134c0-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="134c0-104">A continuación se muestra un ejemplo de un archivo de directivas de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="134c0-104">Here’s an example of a runtime directives file:</span></span>

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

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="134c0-105">Estructura de un archivo de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="134c0-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="134c0-106">El archivo de directivas de tiempo de ejecución utiliza el espacio de nombres `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="134c0-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="134c0-107">El elemento raíz es [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="134c0-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="134c0-108">Puede contener cero o más elementos [Library](library-element-net-native.md) y cero o un elemento [Application](application-element-net-native.md), como se muestra en la estructura siguiente.</span><span class="sxs-lookup"><span data-stu-id="134c0-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="134c0-109">Los atributos del elemento [Application](application-element-net-native.md) pueden definir directivas de reflexión en tiempo de ejecución para toda la aplicación, o puede actuar como contenedor de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="134c0-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="134c0-110">El elemento [Library](library-element-net-native.md), por otro lado, es simplemente un contenedor.</span><span class="sxs-lookup"><span data-stu-id="134c0-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="134c0-111">Los elementos secundarios de los elementos [Application](application-element-net-native.md) y [Library](library-element-net-native.md) definen los tipos, métodos, campos, propiedades y eventos que están disponibles para reflexión.</span><span class="sxs-lookup"><span data-stu-id="134c0-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="134c0-112">Para obtener información de referencia, seleccione los elementos de la siguiente estructura o vea [Runtime Directive Elements](runtime-directive-elements.md) (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="134c0-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="134c0-113">En la siguiente jerarquía, los puntos suspensivos marcan una estructura recursiva.</span><span class="sxs-lookup"><span data-stu-id="134c0-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="134c0-114">La información entre paréntesis indica si el elemento es obligatorio u opcional y, si se utiliza, el número de instancias permitidas (una o varias).</span><span class="sxs-lookup"><span data-stu-id="134c0-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

<span data-ttu-id="134c0-115">[Directivas](directives-element-net-native.md) [[1:1] [](application-element-net-native.md) 0:1] [ensamblado](assembly-element-net-native.md) [0: m] [espacio de nombres](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-115">[Directives](directives-element-net-native.md) [1:1] [Application](application-element-net-native.md) [0:1] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-116">.</span><span class="sxs-lookup"><span data-stu-id="134c0-116">.</span></span> <span data-ttu-id="134c0-117">.</span><span class="sxs-lookup"><span data-stu-id="134c0-117">.</span></span>
<span data-ttu-id="134c0-118">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-118">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-119">.</span><span class="sxs-lookup"><span data-stu-id="134c0-119">.</span></span> <span data-ttu-id="134c0-120">.</span><span class="sxs-lookup"><span data-stu-id="134c0-120">.</span></span>
<span data-ttu-id="134c0-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-122">.</span><span class="sxs-lookup"><span data-stu-id="134c0-122">.</span></span> <span data-ttu-id="134c0-123">.</span><span class="sxs-lookup"><span data-stu-id="134c0-123">.</span></span>
<span data-ttu-id="134c0-124">[Espacio de nombres [0](namespace-element-net-native.md) : m] [espacio de nombres](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-124">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-125">.</span><span class="sxs-lookup"><span data-stu-id="134c0-125">.</span></span> <span data-ttu-id="134c0-126">.</span><span class="sxs-lookup"><span data-stu-id="134c0-126">.</span></span>
<span data-ttu-id="134c0-127">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-127">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-128">.</span><span class="sxs-lookup"><span data-stu-id="134c0-128">.</span></span> <span data-ttu-id="134c0-129">.</span><span class="sxs-lookup"><span data-stu-id="134c0-129">.</span></span>
<span data-ttu-id="134c0-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-131">.</span><span class="sxs-lookup"><span data-stu-id="134c0-131">.</span></span> <span data-ttu-id="134c0-132">.</span><span class="sxs-lookup"><span data-stu-id="134c0-132">.</span></span>
<span data-ttu-id="134c0-133">[Tipos](type-element-net-native.md) [0: m] [subtipos](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1] [tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-133">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-134">.</span><span class="sxs-lookup"><span data-stu-id="134c0-134">.</span></span> <span data-ttu-id="134c0-135">.</span><span class="sxs-lookup"><span data-stu-id="134c0-135">.</span></span>
<span data-ttu-id="134c0-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-137">.</span><span class="sxs-lookup"><span data-stu-id="134c0-137">.</span></span> <span data-ttu-id="134c0-138">.</span><span class="sxs-lookup"><span data-stu-id="134c0-138">.</span></span>
<span data-ttu-id="134c0-139">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1 [] GenericParameter](genericparameter-element-net-native.md) [0: m] [método](method-element-net-native.md) [0: M] [parámetro](parameter-element-net-native.md) [0: m] [TypeParameter](typeparameter-element-net-native.md) [0: m] [GenericParameter](genericparameter-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) ( método genérico construido) [0: M] [propiedad](property-element-net-native.md) [0: m] [campo](field-element-net-native.md) [0: m] [evento](event-element-net-native.md) [0: m] [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: m] [tipo](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-139">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-140">.</span><span class="sxs-lookup"><span data-stu-id="134c0-140">.</span></span> <span data-ttu-id="134c0-141">.</span><span class="sxs-lookup"><span data-stu-id="134c0-141">.</span></span>
<span data-ttu-id="134c0-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-143">.</span><span class="sxs-lookup"><span data-stu-id="134c0-143">.</span></span> <span data-ttu-id="134c0-144">.</span><span class="sxs-lookup"><span data-stu-id="134c0-144">.</span></span>
<span data-ttu-id="134c0-145">[Método](method-element-net-native.md) [0: m] [parámetro](parameter-element-net-native.md) [0: m] [TypeParameter](typeparameter-element-net-native.md) [0: M] [GenericParameter](genericparameter-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0: m] [propiedad](property-element-net-native.md) [0: M] [campo](field-element-net-native.md) [0: m] [evento](event-element-net-native.md) [0: m] [ Biblioteca](library-element-net-native.md) [0: m] [ensamblado](assembly-element-net-native.md) [0: m] [espacio de nombres](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-145">[Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [Library](library-element-net-native.md) [0:M] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-146">.</span><span class="sxs-lookup"><span data-stu-id="134c0-146">.</span></span> <span data-ttu-id="134c0-147">.</span><span class="sxs-lookup"><span data-stu-id="134c0-147">.</span></span>
<span data-ttu-id="134c0-148">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-148">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-149">.</span><span class="sxs-lookup"><span data-stu-id="134c0-149">.</span></span> <span data-ttu-id="134c0-150">.</span><span class="sxs-lookup"><span data-stu-id="134c0-150">.</span></span>
<span data-ttu-id="134c0-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-152">.</span><span class="sxs-lookup"><span data-stu-id="134c0-152">.</span></span> <span data-ttu-id="134c0-153">.</span><span class="sxs-lookup"><span data-stu-id="134c0-153">.</span></span>
<span data-ttu-id="134c0-154">[Espacio de nombres [0](namespace-element-net-native.md) : m] [espacio de nombres](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-154">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-155">.</span><span class="sxs-lookup"><span data-stu-id="134c0-155">.</span></span> <span data-ttu-id="134c0-156">.</span><span class="sxs-lookup"><span data-stu-id="134c0-156">.</span></span>
<span data-ttu-id="134c0-157">[Tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-157">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-158">.</span><span class="sxs-lookup"><span data-stu-id="134c0-158">.</span></span> <span data-ttu-id="134c0-159">.</span><span class="sxs-lookup"><span data-stu-id="134c0-159">.</span></span>
<span data-ttu-id="134c0-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-161">.</span><span class="sxs-lookup"><span data-stu-id="134c0-161">.</span></span> <span data-ttu-id="134c0-162">.</span><span class="sxs-lookup"><span data-stu-id="134c0-162">.</span></span>
<span data-ttu-id="134c0-163">[Tipos](type-element-net-native.md) [0: m] [subtipos](subtypes-element-net-native.md) (subclases del tipo contenedor) [O:1] [tipo](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-163">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-164">.</span><span class="sxs-lookup"><span data-stu-id="134c0-164">.</span></span> <span data-ttu-id="134c0-165">.</span><span class="sxs-lookup"><span data-stu-id="134c0-165">.</span></span>
<span data-ttu-id="134c0-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-167">.</span><span class="sxs-lookup"><span data-stu-id="134c0-167">.</span></span> <span data-ttu-id="134c0-168">.</span><span class="sxs-lookup"><span data-stu-id="134c0-168">.</span></span>
<span data-ttu-id="134c0-169">[AttributeImplies](attributeimplies-element-net-native.md) (el tipo contenedor es un atributo) [O:1 [] GenericParameter](genericparameter-element-net-native.md) [0: m [] método](method-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0: m] [propiedad](property-element-net-native.md) [0: m] [campo](field-element-net-native.md) [0: m] [evento](event-element-net-native.md) [0 : M] [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: m] [tipo](type-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="134c0-169">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="134c0-170">.</span><span class="sxs-lookup"><span data-stu-id="134c0-170">.</span></span> <span data-ttu-id="134c0-171">.</span><span class="sxs-lookup"><span data-stu-id="134c0-171">.</span></span>
<span data-ttu-id="134c0-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (tipo genérico construido) [0: M].</span><span class="sxs-lookup"><span data-stu-id="134c0-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="134c0-173">.</span><span class="sxs-lookup"><span data-stu-id="134c0-173">.</span></span> <span data-ttu-id="134c0-174">.</span><span class="sxs-lookup"><span data-stu-id="134c0-174">.</span></span>
<span data-ttu-id="134c0-175">[Método](method-element-net-native.md) [0: m] [MethodInstantiation](methodinstantiation-element-net-native.md) (método genérico construido) [0: m] [propiedad](property-element-net-native.md) [0: M] [campo](field-element-net-native.md) [0: m] [evento](event-element-net-native.md) [0: m]</span><span class="sxs-lookup"><span data-stu-id="134c0-175">[Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="134c0-176">El elemento [Application](application-element-net-native.md) no puede tener atributos o puede tener los atributos de directiva tratados en la [sección sobre política y directivas de tiempo de ejecución](#Directives).</span><span class="sxs-lookup"><span data-stu-id="134c0-176">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="134c0-177">Un elemento [Library](library-element-net-native.md) tiene un solo atributo, `Name`, que especifica el nombre de una biblioteca o ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="134c0-177">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="134c0-178">Por ejemplo, el siguiente elemento [Library](library-element-net-native.md) se aplica a un ensamblado denominado Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="134c0-178">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

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

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="134c0-179">Política y directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="134c0-179">Runtime directives and policy</span></span>

<span data-ttu-id="134c0-180">El elemento [Application](application-element-net-native.md) y los elementos secundarios de los elementos [Library](library-element-net-native.md) y [Application](application-element-net-native.md) expresan directiva; es decir, definen la forma en que una aplicación puede aplicar reflexión a un elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="134c0-180">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="134c0-181">El tipo de la directiva se define mediante un atributo del elemento (por ejemplo, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="134c0-181">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="134c0-182">El valor de la directiva se define mediante el valor del atributo (por ejemplo, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="134c0-182">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="134c0-183">Cualquier directiva especificada por un atributo de un elemento se aplica a todos los elementos secundarios que no especifican ningún valor para esa directiva.</span><span class="sxs-lookup"><span data-stu-id="134c0-183">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="134c0-184">Por ejemplo, si una directiva se especifica mediante un elemento [Type](type-element-net-native.md), esa directiva se aplica a todos los tipos y miembros contenidos para los que no se especifica explícitamente una directiva.</span><span class="sxs-lookup"><span data-stu-id="134c0-184">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="134c0-185">La directiva que puede expresarse mediante los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) difiere de la que puede expresarse para miembros individuales (mediante los elementos [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) y [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="134c0-185">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="134c0-186">Especificar la directiva para ensamblados, espacios de nombres y tipos</span><span class="sxs-lookup"><span data-stu-id="134c0-186">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="134c0-187">Los elementos [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) y [Type](type-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="134c0-187">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="134c0-188">`Activate`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-188">`Activate`.</span></span> <span data-ttu-id="134c0-189">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de las instancias.</span><span class="sxs-lookup"><span data-stu-id="134c0-189">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="134c0-190">`Browse`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-190">`Browse`.</span></span> <span data-ttu-id="134c0-191">Controla la consulta de información sobre elementos del programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="134c0-191">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="134c0-192">`Dynamic`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-192">`Dynamic`.</span></span> <span data-ttu-id="134c0-193">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="134c0-193">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="134c0-194">`Serialize`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-194">`Serialize`.</span></span> <span data-ttu-id="134c0-195">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades, para permitir que bibliotecas de terceros (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="134c0-195">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="134c0-196">`DataContractSerializer`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-196">`DataContractSerializer`.</span></span> <span data-ttu-id="134c0-197">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="134c0-197">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="134c0-198">`DataContractJsonSerializer`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-198">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="134c0-199">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="134c0-199">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="134c0-200">`XmlSerializer`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-200">`XmlSerializer`.</span></span> <span data-ttu-id="134c0-201">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="134c0-201">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="134c0-202">`MarshalObject`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-202">`MarshalObject`.</span></span> <span data-ttu-id="134c0-203">Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="134c0-203">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="134c0-204">`MarshalDelegate`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-204">`MarshalDelegate`.</span></span> <span data-ttu-id="134c0-205">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="134c0-205">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="134c0-206">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="134c0-206">`MarshalStructure` .</span></span> <span data-ttu-id="134c0-207">Controla la directiva para calcular referencias de estructuras a código nativo.</span><span class="sxs-lookup"><span data-stu-id="134c0-207">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="134c0-208">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="134c0-208">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="134c0-209">`All`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-209">`All`.</span></span> <span data-ttu-id="134c0-210">Habilita la directiva para todos los tipos y miembros que no se eliminan con la cadena de herramientas.</span><span class="sxs-lookup"><span data-stu-id="134c0-210">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="134c0-211">`Auto`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-211">`Auto`.</span></span> <span data-ttu-id="134c0-212">Usa el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="134c0-212">Use the default behavior.</span></span> <span data-ttu-id="134c0-213">(No especificar una directiva es equivalente a establecer esa directiva en `Auto`, a menos que se invalide la directiva, por ejemplo, por un elemento primario).</span><span class="sxs-lookup"><span data-stu-id="134c0-213">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="134c0-214">`Excluded`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-214">`Excluded`.</span></span> <span data-ttu-id="134c0-215">Deshabilita la directiva para el elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="134c0-215">Disable the policy for the program element.</span></span>

- <span data-ttu-id="134c0-216">`Public`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-216">`Public`.</span></span> <span data-ttu-id="134c0-217">Habilita la directiva para tipos o miembros públicos a menos que la cadena de herramientas determine que el miembro es innecesario y, por tanto, lo quita.</span><span class="sxs-lookup"><span data-stu-id="134c0-217">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="134c0-218">(En este último caso, debe utilizar `Required Public` para asegurarse de que el miembro se conserva y tiene capacidades de reflexión).</span><span class="sxs-lookup"><span data-stu-id="134c0-218">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="134c0-219">`PublicAndInternal`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-219">`PublicAndInternal`.</span></span> <span data-ttu-id="134c0-220">Habilita la directiva para tipos o miembros públicos e internos si la cadena de herramientas no los quita.</span><span class="sxs-lookup"><span data-stu-id="134c0-220">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="134c0-221">`Required Public`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-221">`Required Public`.</span></span> <span data-ttu-id="134c0-222">Exige que la cadena de herramientas mantenga los tipos y miembros públicos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="134c0-222">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="134c0-223">`Required PublicAndInternal`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-223">`Required PublicAndInternal`.</span></span> <span data-ttu-id="134c0-224">Exige que la cadena de herramientas mantenga los tipos y miembros públicos e internos tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="134c0-224">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="134c0-225">`Required All`Operador</span><span class="sxs-lookup"><span data-stu-id="134c0-225">`Required All`.</span></span> <span data-ttu-id="134c0-226">Exige que la cadena de herramientas mantenga todos los tipos y miembros tanto si se utilizan como si no, y habilita la directiva para ellos.</span><span class="sxs-lookup"><span data-stu-id="134c0-226">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="134c0-227">Por ejemplo, el siguiente archivo de directivas de tiempo de ejecución define una directiva para todos los tipos y miembros del ensamblado DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="134c0-227">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="134c0-228">Permite reflexión para la serialización de todas las propiedades públicas, permite buscar todos los tipos y miembros de tipo, permite la activación para todos los tipos (debido al atributo `Dynamic`) y permite la reflexión para todos los tipos y miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="134c0-228">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

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

### <a name="specifying-policy-for-members"></a><span data-ttu-id="134c0-229">Especificar la directiva para los miembros</span><span class="sxs-lookup"><span data-stu-id="134c0-229">Specifying policy for members</span></span>

<span data-ttu-id="134c0-230">Los elementos [Property](property-element-net-native.md) y [Field](field-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="134c0-230">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="134c0-231">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="134c0-231">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="134c0-232">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="134c0-232">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="134c0-233">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="134c0-233">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="134c0-234">`Serialize`: controla el acceso en tiempo de ejecución al miembro para permitir que las bibliotecas (como el serializador de JSON Newtonsoft) puedan serializar y deserializar las instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="134c0-234">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="134c0-235">Esta directiva puede aplicarse a propiedades, campos y constructores.</span><span class="sxs-lookup"><span data-stu-id="134c0-235">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="134c0-236">Los elementos [Method](method-element-net-native.md) y [Event](event-element-net-native.md) admiten los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="134c0-236">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="134c0-237">`Browse`: controla la consulta de información sobre este miembro, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="134c0-237">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="134c0-238">`Dynamic`: controla el acceso en tiempo de ejecución a todos los miembros de tipos, incluidos constructores, métodos, campos, propiedades y eventos, para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="134c0-238">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="134c0-239">También controla la consulta de información sobre el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="134c0-239">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="134c0-240">Los valores asociados con estos tipos de directiva son:</span><span class="sxs-lookup"><span data-stu-id="134c0-240">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="134c0-241">`Auto`: usar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="134c0-241">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="134c0-242">(No especificar una política es equivalente a establecer esa directiva en `Auto`, a menos que algo la invalide).</span><span class="sxs-lookup"><span data-stu-id="134c0-242">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="134c0-243">`Excluded`: no incluir nunca metadatos para el miembro.</span><span class="sxs-lookup"><span data-stu-id="134c0-243">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="134c0-244">`Included`: habilitar la directiva, si el tipo primario está presente en la salida.</span><span class="sxs-lookup"><span data-stu-id="134c0-244">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="134c0-245">`Required`: exige que la cadena de herramientas mantenga este miembro incluso si no parece usado, y habilitar una directiva para él.</span><span class="sxs-lookup"><span data-stu-id="134c0-245">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="134c0-246">Semántica de archivos de directivas de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="134c0-246">Runtime directives file semantics</span></span>

<span data-ttu-id="134c0-247">La directiva puede definirse simultáneamente para elementos de nivel superior y de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="134c0-247">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="134c0-248">Por ejemplo, puede definirse la directiva de un ensamblado y de algunos de los tipos contenidos en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="134c0-248">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="134c0-249">Si un elemento determinado de nivel inferior no está representado, hereda la directiva de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="134c0-249">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="134c0-250">Por ejemplo, si un elemento `Assembly` está presente pero el elemento `Type` no, la directiva especificada en el elemento `Assembly` se aplica a cada tipo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="134c0-250">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="134c0-251">Varios elementos también pueden aplicar una directiva al mismo elemento de programa.</span><span class="sxs-lookup"><span data-stu-id="134c0-251">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="134c0-252">Por ejemplo, es posible que distintos elementos [Assembly](assembly-element-net-native.md) definan el mismo elemento de directiva para el mismo ensamblado de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="134c0-252">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="134c0-253">Las siguientes secciones explican cómo se resuelve la directiva para un tipo concreto en esos casos.</span><span class="sxs-lookup"><span data-stu-id="134c0-253">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="134c0-254">Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) de un tipo o método genérico aplica su directiva a todas las creaciones de instancias que no tienen su propia directiva.</span><span class="sxs-lookup"><span data-stu-id="134c0-254">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="134c0-255">Por ejemplo, un elemento `Type` que especifica la directiva de <xref:System.Collections.Generic.List%601> se aplica a todas las instancias construidas de ese tipo genérico, a menos que un elemento `List<Int32>` las invalide para un determinado tipo genérico construido (como un `TypeInstantiation`).</span><span class="sxs-lookup"><span data-stu-id="134c0-255">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="134c0-256">De lo contrario, los elementos definen la directiva para el elemento de programa denominado.</span><span class="sxs-lookup"><span data-stu-id="134c0-256">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="134c0-257">Cuando un elemento es ambiguo, el motor busca coincidencias y, si encuentra a una coincidencia exacta, la utiliza.</span><span class="sxs-lookup"><span data-stu-id="134c0-257">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="134c0-258">Si encuentra a varias coincidencias, habrá una advertencia o un error.</span><span class="sxs-lookup"><span data-stu-id="134c0-258">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="134c0-259">Si dos directivas directiva se aplican al mismo elemento de programa</span><span class="sxs-lookup"><span data-stu-id="134c0-259">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="134c0-260">Si dos elementos de diferentes archivos de directivas de tiempo de ejecución intentan establecer el mismo tipo de directiva para el mismo elemento de programa (por ejemplo, un ensamblado o tipo) en valores diferentes, el conflicto se resuelve como sigue:</span><span class="sxs-lookup"><span data-stu-id="134c0-260">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="134c0-261">Si el elemento `Excluded` está presente, tiene precedencia.</span><span class="sxs-lookup"><span data-stu-id="134c0-261">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="134c0-262">`Required` tiene precedencia sobre no `Required`.</span><span class="sxs-lookup"><span data-stu-id="134c0-262">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="134c0-263">`All` tiene precedencia sobre `PublicAndInternal`, que tiene precedencia sobre `Public`.</span><span class="sxs-lookup"><span data-stu-id="134c0-263">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="134c0-264">Cualquier valor explícito tiene precedencia sobre `Auto`.</span><span class="sxs-lookup"><span data-stu-id="134c0-264">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="134c0-265">Por ejemplo, si un único proyecto incluye los dos archivos de directivas de tiempo de ejecución siguientes, la directiva de serialización para DataClasses.dll se establece tanto en `Required Public` como en `All`.</span><span class="sxs-lookup"><span data-stu-id="134c0-265">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="134c0-266">En este caso, la directiva de serialización se puede resolver como `Required All`.</span><span class="sxs-lookup"><span data-stu-id="134c0-266">In this case, the serialization policy would be resolved as `Required All`.</span></span>

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

<span data-ttu-id="134c0-267">Sin embargo, si dos directivas de un único archivo de directivas de tiempo de ejecución intenta establecer el mismo tipo de directiva para el mismo elemento de programa, la herramienta de definición de esquema XML muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="134c0-267">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="134c0-268">Si elementos primarios y secundarios aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="134c0-268">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="134c0-269">Los elementos secundarios invalidan a sus elementos primarios, incluido el valor `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="134c0-269">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="134c0-270">La invalidación es la razón principal por la que desearía especificar `Auto`.</span><span class="sxs-lookup"><span data-stu-id="134c0-270">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="134c0-271">En el siguiente ejemplo, el valor de directiva de serialización para todo lo contenido en `DataClasses` que no está en `DataClasses.ViewModels` sería `Required Public`, y todo lo que está tanto en `DataClasses` como en `DataClasses.ViewModels` sería `All`.</span><span class="sxs-lookup"><span data-stu-id="134c0-271">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

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

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="134c0-272">Si los genéricos abiertos y elementos con instancia aplican el mismo tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="134c0-272">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="134c0-273">En el siguiente ejemplo, la directiva `Dictionary<int,int>` se asigna a `Browse` solo si el motor tiene otra razón para darle otorgarle la directiva `Browse` (que de lo contrario sería el comportamiento predeterminado); todos los miembros del resto de creaciones de instancias de <xref:System.Collections.Generic.Dictionary%602> se podrán examinar.</span><span class="sxs-lookup"><span data-stu-id="134c0-273">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

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

### <a name="how-policy-is-inferred"></a><span data-ttu-id="134c0-274">Cómo se infiere la directiva</span><span class="sxs-lookup"><span data-stu-id="134c0-274">How policy is inferred</span></span>

<span data-ttu-id="134c0-275">Cada tipo de directiva tiene un conjunto diferente de reglas que determinan cómo la presencia de ese tipo de directiva afecta a otras construcciones.</span><span class="sxs-lookup"><span data-stu-id="134c0-275">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="134c0-276">El efecto de la directiva Browse</span><span class="sxs-lookup"><span data-stu-id="134c0-276">The effect of Browse policy</span></span>

<span data-ttu-id="134c0-277">Aplicar la directiva `Browse` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-277">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-278">El tipo base del tipo que está marcado con directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-278">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-279">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-279">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-280">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-280">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-281">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-281">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-282">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-282">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-283">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-283">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-284">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-284">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="134c0-285">Aplicar la directiva `Browse` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-285">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-286">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-286">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-287">El tipo devuelto del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-287">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-288">El tipo contenedor del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-288">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-289">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-289">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-290">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-290">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-291">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-291">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-292">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-292">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="134c0-293">Aplicar la directiva `Browse` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-293">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-294">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-294">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-295">El tipo del campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-295">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-296">El tipo al que pertenece el campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-296">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="134c0-297">Efecto de la directiva Dynamic</span><span class="sxs-lookup"><span data-stu-id="134c0-297">The effect of Dynamic policy</span></span>

<span data-ttu-id="134c0-298">Aplicar la directiva `Dynamic` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-298">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-299">El tipo base del tipo que está marcado con directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-299">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-300">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-300">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-301">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-301">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-302">Cada interfaz del tipo que está marcado con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-302">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-303">El tipo de cada atributo que se aplica al tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-303">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-304">Si el tipo es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-304">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-305">Si el tipo es genérico, los tipos sobre los cuales se crea una instancia del tipo se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-305">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="134c0-306">Aplicar la directiva `Dynamic` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-306">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-307">Cada tipo de parámetro del método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-307">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-308">El tipo devuelto del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-308">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-309">El tipo contenedor del método se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-309">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-310">Si el método es método genérico para el que se creó una instancia, el método genérico sin instancia se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-310">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-311">El tipo de cada atributo que se aplica al método se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-311">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-312">Si el método es genérico, cada tipo de restricción se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-312">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-313">Si el método es genérico, los tipos sobre los cuales se crea una instancia del método se marcan con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-313">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-314">`MethodInfo.Invoke` puede invocar al método y la creación de delegados se hace posible mediante <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="134c0-314">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="134c0-315">Aplicar la directiva `Dynamic` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-315">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-316">El tipo de cada atributo que se aplica al campo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-316">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-317">El tipo del campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-317">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-318">El tipo al que pertenece el campo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-318">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="134c0-319">Efecto de la directiva Activation</span><span class="sxs-lookup"><span data-stu-id="134c0-319">The effect of Activation policy</span></span>

<span data-ttu-id="134c0-320">Aplicar la directiva Activation a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-320">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-321">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-322">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-322">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-323">Los constructores del tipo se marcan con la directiva `Activation`.</span><span class="sxs-lookup"><span data-stu-id="134c0-323">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="134c0-324">Aplicar la directiva `Activation` a un método implica el siguiente cambio de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-324">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="134c0-325">El constructor puede invocarse mediante los métodos <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> y <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="134c0-325">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="134c0-326">En cuanto a los métodos, la directiva `Activation` solo afecta a constructores.</span><span class="sxs-lookup"><span data-stu-id="134c0-326">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="134c0-327">Aplicar la directiva `Activation` a un campo no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="134c0-327">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="134c0-328">Efecto de la directiva Serialize</span><span class="sxs-lookup"><span data-stu-id="134c0-328">The effect of Serialize policy</span></span>

<span data-ttu-id="134c0-329">La directiva `Serialize` permite el uso de serializadores comunes basados en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="134c0-329">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="134c0-330">Sin embargo, dado que Microsoft no conoce los patrones de acceso reflejo exacto de los serializadores que no son de Microsoft, esta directiva puede no ser totalmente efectiva.</span><span class="sxs-lookup"><span data-stu-id="134c0-330">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="134c0-331">Aplicar la directiva `Serialize` a un tipo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-331">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-332">El tipo base del tipo que está marcado con directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-332">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-333">Si el tipo es un genérico con instancia, la versión sin instancia del tipo se marca con la directiva `Browse`.</span><span class="sxs-lookup"><span data-stu-id="134c0-333">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="134c0-334">Si el tipo es un delegado, el método `Invoke` en el tipo se marca con la directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="134c0-334">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="134c0-335">Si el tipo es una enumeración, una matriz del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-335">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-336">Si el tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-336">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-337">Si el tipo es <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, entonces `T[]` y <xref:System.Collections.Generic.List%601> se marcan con la directiva `Serialize`. Sin embargo, ningún miembro del tipo de interfaz se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-337">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-338">Si el tipo es <xref:System.Collections.Generic.List%601>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-338">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-339">Si el tipo es <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-339">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="134c0-340">En cambio, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-340">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-341">Si el tipo es <xref:System.Collections.Generic.Dictionary%602>, ningún miembro del tipo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-341">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-342">Si el tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` y `TValue` se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-342">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-343">Todos los constructores, todos los descriptores de acceso de propiedad y todos los campos se marcan con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-343">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="134c0-344">Aplicar la directiva `Serialize` a un método implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-344">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-345">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-345">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-346">El tipo devuelto del método se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-346">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="134c0-347">Aplicar la directiva `Serialize` a un campo implica los siguientes cambios de directiva:</span><span class="sxs-lookup"><span data-stu-id="134c0-347">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="134c0-348">El tipo contenedor se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-348">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="134c0-349">El tipo del campo se marca con la directiva `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="134c0-349">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="134c0-350">Efecto de las directivas XmlSerializer, DataContractSerializer y DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="134c0-350">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="134c0-351">A diferencia de la Directiva de `Serialize`, que está destinada a los serializadores basados en reflexión, las directivas <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> se utilizan para habilitar un conjunto de serializadores conocidos para la cadena de herramientas de .NET Native.</span><span class="sxs-lookup"><span data-stu-id="134c0-351">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="134c0-352">Estos serializadores no se implementan mediante reflexión, pero el conjunto de tipos que se pueden serializar en tiempo de ejecución se determina de manera similar a los tipos que admiten reflexión.</span><span class="sxs-lookup"><span data-stu-id="134c0-352">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="134c0-353">Aplicar una de estas directivas a un tipo permite la serialización del tipo con el serializador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="134c0-353">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="134c0-354">Además, los tipos que el motor de serialización puede determinar de forma estática que necesitan serialización también se podrán serializar.</span><span class="sxs-lookup"><span data-stu-id="134c0-354">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="134c0-355">Estas directivas no tienen efecto sobre los campos o métodos.</span><span class="sxs-lookup"><span data-stu-id="134c0-355">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="134c0-356">Para más información, vea la sección "Diferencias en los serializadores" en [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="134c0-356">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="134c0-357">Vea también</span><span class="sxs-lookup"><span data-stu-id="134c0-357">See also</span></span>

- [<span data-ttu-id="134c0-358">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="134c0-358">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="134c0-359">Reflexión y .NET Native</span><span class="sxs-lookup"><span data-stu-id="134c0-359">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

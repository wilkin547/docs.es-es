---
title: Directiva de x:Property
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: d4294b39ff262198f8082863d23eb6f4edbc7054
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549306"
---
# <a name="xproperty-directive"></a><span data-ttu-id="75e2c-102">Directiva de x:Property</span><span class="sxs-lookup"><span data-stu-id="75e2c-102">x:Property Directive</span></span>

<span data-ttu-id="75e2c-103">Declara una propiedad XAML en el marcado.</span><span class="sxs-lookup"><span data-stu-id="75e2c-103">Declares a XAML property in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="75e2c-104">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="75e2c-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="75e2c-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="75e2c-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="75e2c-106">Nombre de la clase de respaldo o clase parcial para la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="75e2c-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`propertyName`|<span data-ttu-id="75e2c-107">Nombre del miembro de la propiedad que se define.</span><span class="sxs-lookup"><span data-stu-id="75e2c-107">Member name of the property being defined.</span></span>|
|`propertyType`|<span data-ttu-id="75e2c-108">Nombre del tipo (u otra forma de cadena, específica del marco) que especifica el tipo de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="75e2c-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="75e2c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75e2c-109">Remarks</span></span>

<span data-ttu-id="75e2c-110">En la implementación de servicios XAML de .NET,.</span><span class="sxs-lookup"><span data-stu-id="75e2c-110">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="75e2c-111">`x:Property` no tiene un respaldo de tipos directo pero es compatible con la clase <xref:System.Windows.Markup.PropertyDefinition>.</span><span class="sxs-lookup"><span data-stu-id="75e2c-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="75e2c-112">En un flujo de nodo XAML, un elemento `x:Property` se representa como un miembro llamado `Property`, del espacio de nombres XAML de lenguaje XAML.</span><span class="sxs-lookup"><span data-stu-id="75e2c-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="75e2c-113">El miembro `Property` contiene atributos tal y como declara el marcado.</span><span class="sxs-lookup"><span data-stu-id="75e2c-113">The member `Property` hold attributes as declared by markup.</span></span>

<span data-ttu-id="75e2c-114">El significado de `Name` y `Type` no se asigna en el nivel de servicios XAML de .net.</span><span class="sxs-lookup"><span data-stu-id="75e2c-114">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="75e2c-115">Se almacenan en el flujo de nodo XAML inicial como valores de cadena, para ser interpretados posteriormente conforme a las reglas que puedan imponer marcos concretos.</span><span class="sxs-lookup"><span data-stu-id="75e2c-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="75e2c-116">El significado puede alinearse con un nombre XAML y un significado de tipo XAML, o puede ser válido solo en un sistema de tipos de respaldo, dependiendo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="75e2c-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="75e2c-117">Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar.</span><span class="sxs-lookup"><span data-stu-id="75e2c-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="75e2c-118">El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="75e2c-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="75e2c-119">Sin embargo, el mecanismo para asociar tipos y miembros o para producir definiciones de miembros dinámicos no se admite en el nivel de servicios XAML de .NET.</span><span class="sxs-lookup"><span data-stu-id="75e2c-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="75e2c-120">De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML.</span><span class="sxs-lookup"><span data-stu-id="75e2c-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="75e2c-121">Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.</span><span class="sxs-lookup"><span data-stu-id="75e2c-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="75e2c-122">x:Property para Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="75e2c-122">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="75e2c-123">Para Windows Workflow Foundation, `x:Property` define los miembros de una actividad personalizada compuesta completamente en XAML o XAML, con miembros dinámicos definidos para un diseñador de actividades con código subyacente.</span><span class="sxs-lookup"><span data-stu-id="75e2c-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="75e2c-124">`x:Class` también se debe especificar en el elemento raíz de la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="75e2c-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="75e2c-125">Esto no es un requisito en el nivel de servicios XAML de .NET, pero se convierte en un requisito cuando la producción de XAML se carga mediante las acciones de compilación de MSBUILD que admiten las actividades personalizadas y Windows Workflow Foundation XAML en general.</span><span class="sxs-lookup"><span data-stu-id="75e2c-125">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="75e2c-126">Windows Workflow Foundation no utiliza el nombre de tipo XAML puro como valor previsto para el `x:Property` `Type` atributo y, en su lugar, utiliza una Convención que no se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="75e2c-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="75e2c-127">Para obtener más información, vea [creación de DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="75e2c-127">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>

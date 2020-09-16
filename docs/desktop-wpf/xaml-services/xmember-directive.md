---
title: Directiva de x:Member
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: 1c5b26b405e574290af54b29b22fb5e19e4b6b95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548252"
---
# <a name="xmember-directive"></a><span data-ttu-id="efef0-102">Directiva de x:Member</span><span class="sxs-lookup"><span data-stu-id="efef0-102">x:Member Directive</span></span>
<span data-ttu-id="efef0-103">Declara un miembro XAML en el marcado.</span><span class="sxs-lookup"><span data-stu-id="efef0-103">Declares a XAML member in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="efef0-104">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="efef0-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="efef0-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="efef0-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="efef0-106">Nombre de la clase de respaldo o clase parcial para la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="efef0-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`memberName`|<span data-ttu-id="efef0-107">Nombre del miembro de la propiedad que se define.</span><span class="sxs-lookup"><span data-stu-id="efef0-107">Member name of the property being defined.</span></span>|

## <a name="remarks"></a><span data-ttu-id="efef0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efef0-108">Remarks</span></span>

<span data-ttu-id="efef0-109">En la implementación de servicios XAML de .NET,.</span><span class="sxs-lookup"><span data-stu-id="efef0-109">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="efef0-110">`x:Member` no tiene un respaldo de tipos directo pero es compatible con la clase <xref:System.Windows.Markup.MemberDefinition>.</span><span class="sxs-lookup"><span data-stu-id="efef0-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="efef0-111">En un flujo de nodo XAML, un elemento `x:Member` se representa como un miembro llamado `Member`, del espacio de nombres XAML de lenguaje XAML.</span><span class="sxs-lookup"><span data-stu-id="efef0-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="efef0-112">El miembro `Member` contiene atributos tal y como declara el marcado.</span><span class="sxs-lookup"><span data-stu-id="efef0-112">The member `Member` holds attributes as declared by markup.</span></span>

<span data-ttu-id="efef0-113">El significado de `Name` y `Type` no se asigna en el nivel de servicios XAML de .net.</span><span class="sxs-lookup"><span data-stu-id="efef0-113">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="efef0-114">Se almacenan en el flujo de nodo XAML inicial como valores de cadena, para ser interpretados posteriormente conforme a las reglas que puedan imponer marcos concretos.</span><span class="sxs-lookup"><span data-stu-id="efef0-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="efef0-115">El significado puede alinearse con un nombre XAML y un significado de tipo XAML, o puede ser válido solo en un sistema de tipos de respaldo, dependiendo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="efef0-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="efef0-116">Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar.</span><span class="sxs-lookup"><span data-stu-id="efef0-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="efef0-117">El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="efef0-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="efef0-118">Sin embargo, el mecanismo para asociar tipos y miembros o para producir definiciones de miembros dinámicos no se admite en el nivel de servicios XAML de .NET.</span><span class="sxs-lookup"><span data-stu-id="efef0-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="efef0-119">De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML.</span><span class="sxs-lookup"><span data-stu-id="efef0-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="efef0-120">Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.</span><span class="sxs-lookup"><span data-stu-id="efef0-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="efef0-121">x:Property para Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="efef0-121">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="efef0-122">Para Windows Workflow Foundation, `x:Property` define los miembros de una actividad personalizada compuesta completamente en XAML o XAML, con miembros dinámicos definidos para un diseñador de actividades con código subyacente.</span><span class="sxs-lookup"><span data-stu-id="efef0-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="efef0-123">`x:Class` también se debe especificar en el elemento raíz de la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="efef0-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="efef0-124">Esto no es un requisito en el nivel de servicios XAML de .NET, pero se convierte en un requisito cuando la producción de XAML se carga mediante las acciones de compilación de MSBUILD que admiten las actividades personalizadas y Windows Workflow Foundation XAML en general.</span><span class="sxs-lookup"><span data-stu-id="efef0-124">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="efef0-125">Windows Workflow Foundation no utiliza el nombre de tipo XAML puro como valor previsto para el `x:Property` `Type` atributo y, en su lugar, utiliza una Convención que no se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="efef0-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="efef0-126">Para obtener más información, vea [creación de DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="efef0-126">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>

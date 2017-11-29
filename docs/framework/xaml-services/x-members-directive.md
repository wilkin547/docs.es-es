---
title: Directiva de x:Members
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 230c6359c59b9f00738de9ce7ceeccd69899135f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xmembers-directive"></a><span data-ttu-id="fa63d-102">Directiva de x:Members</span><span class="sxs-lookup"><span data-stu-id="fa63d-102">x:Members Directive</span></span>
<span data-ttu-id="fa63d-103">Contiene un conjunto de miembros que se definen en el marcado, que se aplican para el atributo x: Class del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="fa63d-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fa63d-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="fa63d-104">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fa63d-105">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="fa63d-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="fa63d-106">Nombre de la clase de respaldo o clase parcial para la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="fa63d-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="fa63d-107">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="fa63d-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="fa63d-108">Uno o más elementos de objeto que representan las definiciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="fa63d-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="fa63d-109">Normalmente, estos son `x:Property` elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="fa63d-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="fa63d-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="fa63d-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa63d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa63d-111">Remarks</span></span>  
 <span data-ttu-id="fa63d-112">En la implementación de servicios XAML de .NET Framework, no hay ninguna clase de respaldo o la implementación subyacente de un miembro para `x:Members`.</span><span class="sxs-lookup"><span data-stu-id="fa63d-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="fa63d-113">`x:Members`es un miembro XAML especiales que puede existir como un miembro de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="fa63d-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="fa63d-114">En un flujo de nodo XAML, `x:Members` se representa como un miembro denominado `Members`, desde el espacio de nombres XAML de lenguaje XAML.</span><span class="sxs-lookup"><span data-stu-id="fa63d-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="fa63d-115">El miembro `Members` contiene una lista genérica de solo lectura de `Member` objetos.</span><span class="sxs-lookup"><span data-stu-id="fa63d-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="fa63d-116">En el marcado típica se especifican los miembros individuales como `x:Property` elementos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa63d-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="fa63d-117">`x:Property`es un tipo más preciso específicamente para las propiedades de tipos y se puede asignar a `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="fa63d-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="fa63d-118">Para obtener más información, consulte [Directiva x: Property](../../../docs/framework/xaml-services/x-property-directive.md).</span><span class="sxs-lookup"><span data-stu-id="fa63d-118">For more information, see [x:Property Directive](../../../docs/framework/xaml-services/x-property-directive.md).</span></span>  
  
 <span data-ttu-id="fa63d-119">Para admitir un uso práctico de `x:Members` como medio para especificar definiciones de miembros en el marcado, los miembros deben asociarse con una clase que se pueda modificar.</span><span class="sxs-lookup"><span data-stu-id="fa63d-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="fa63d-120">El modelo previsto es que `x:Members` exista como miembro de un tipo que especifica una `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="fa63d-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="fa63d-121">Sin embargo, el mecanismo para asociar tipos y miembros o para generar definiciones de miembros dinámicas no se admite en el nivel de los servicios XAML de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa63d-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="fa63d-122">De esto se encargan los marcos individuales que tienen modelos de aplicación compatibles con las definiciones de miembro de XAML.</span><span class="sxs-lookup"><span data-stu-id="fa63d-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="fa63d-123">Normalmente, para admitir esta característica se necesitan acciones de compilación de MSBUILD que compilan XAML por marcado y, o bien lo integran con código subyacente o producen ensamblados puros a partir de XAML.</span><span class="sxs-lookup"><span data-stu-id="fa63d-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="fa63d-124">x: Members para Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="fa63d-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="fa63d-125">Para Windows Workflow Foundation, `x:Members` contiene los miembros de una actividad personalizada compuesta completamente en XAML o XAML: miembros dinámicos definidos para un diseñador de actividades con código subyacente.</span><span class="sxs-lookup"><span data-stu-id="fa63d-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="fa63d-126">`x:Class` también se debe especificar en el elemento raíz de la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="fa63d-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="fa63d-127">Esto no es un requisito de los servicios XAML de .NET Framework, pero es obligatorio cuando la producción de XAML se carga mediante las acciones de compilación de MSBUILD que admiten actividades personalizadas y XAML en Windows Workflow Foundation en general.</span><span class="sxs-lookup"><span data-stu-id="fa63d-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="fa63d-128">`x:Members`debe ser el primer elemento secundario en el marcado del elemento de objeto que declara el `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="fa63d-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>

---
title: x:Subclass (Directiva)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 566b772db0e8f96c3272481d47b3e220f727d95b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="xsubclass-directive"></a><span data-ttu-id="3ccd3-102">x:Subclass (Directiva)</span><span class="sxs-lookup"><span data-stu-id="3ccd3-102">x:Subclass Directive</span></span>
<span data-ttu-id="3ccd3-103">Modifica el comportamiento de compilación de marcado XAML cuando `x:Class` también se proporciona.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="3ccd3-104">En lugar de crear una clase parcial que se basa en `x:Class`, proporcionado `x:Class` se crea como una clase intermedia, y, a continuación, se espera que la clase derivada proporcionada basarse en `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3ccd3-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="3ccd3-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3ccd3-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="3ccd3-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="3ccd3-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-107">Optional.</span></span> <span data-ttu-id="3ccd3-108">Especifica un espacio de nombres CLR que contiene `classname`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="3ccd3-109">Si `namespace` se especifica un punto (.) separa `namespace` y `classname`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|  
|`classname`|<span data-ttu-id="3ccd3-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-110">Required.</span></span> <span data-ttu-id="3ccd3-111">Especifica el nombre de la clase parcial que conecta el XAML cargado y el código subyacente de ese XAML CLR.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="3ccd3-112">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-112">See Remarks.</span></span>|  
|`subclassNamespace`|<span data-ttu-id="3ccd3-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-113">Optional.</span></span> <span data-ttu-id="3ccd3-114">Puede ser diferente de `namespace` si cada espacio de nombres puede resolver el otro.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="3ccd3-115">Especifica un espacio de nombres CLR que contiene `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="3ccd3-116">Si `subclassName` se especifica un punto (.) separa `subclassNamespace` y `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|  
|`subclassName`|<span data-ttu-id="3ccd3-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-117">Required.</span></span> <span data-ttu-id="3ccd3-118">Especifica el nombre de la subclase CLR.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-118">Specifies the CLR name of the subclass.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="3ccd3-119">Dependencias</span><span class="sxs-lookup"><span data-stu-id="3ccd3-119">Dependencies</span></span>  
 <span data-ttu-id="3ccd3-120">[x: Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar en el mismo objeto, y ese objeto debe ser el elemento raíz de la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-120">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ccd3-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ccd3-121">Remarks</span></span>  
 <span data-ttu-id="3ccd3-122">`x:Subclass` uso sirve principalmente para los lenguajes que no admiten las declaraciones de clase parcial.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>  
  
 <span data-ttu-id="3ccd3-123">La clase se utiliza como el `x:Subclass` no puede ser una clase anidada, y `x:Subclass` debe hacer referencia al objeto raíz como se explica en la sección "Dependencias".</span><span class="sxs-lookup"><span data-stu-id="3ccd3-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>  
  
 <span data-ttu-id="3ccd3-124">En caso contrario, el significado conceptual de `x:Subclass` no está definida por una implementación de servicios XAML de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET Framework XAML Services implementation.</span></span> <span data-ttu-id="3ccd3-125">Esto es porque el comportamiento de servicios XAML de .NET Framework no especifica el modelo de programación general que XAML marcado y código de respaldo están conectados.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-125">This is because .NET Framework XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="3ccd3-126">Relacionados con las implementaciones de conceptos más extensos `x:Class` y `x:Subclass` se realizan marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML, marcado compilado y código subyacente basado en CLR.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="3ccd3-127">Cada marco de trabajo podría tener sus propias acciones de compilación que habilitan algunos de los comportamientos o componentes específicos que deben incluirse en el entorno de compilación.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="3ccd3-128">Dentro de un marco de trabajo, acciones de compilación también pueden variar según el lenguaje CLR específico que se utiliza para el código subyacente.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="3ccd3-129">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="3ccd3-129">WPF Usage Notes</span></span>  
 <span data-ttu-id="3ccd3-130">`x:Subclass` puede estar en una raíz de la página o en la <xref:System.Windows.Application> raíz en la definición de aplicación, que ya tiene `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="3ccd3-131">Declarar `x:Subclass` en cualquier elemento que no sea una raíz de aplicación o página, o bien especificándolo donde no `x:Class` existe, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>  
  
 <span data-ttu-id="3ccd3-132">Crear derivada de las clases que funcionan correctamente para el `x:Subclass` escenario es bastante compleja.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="3ccd3-133">Debe examinar los archivos intermedios (los archivos. g generados en la carpeta obj del proyecto mediante la compilación de marcado, con nombres que incorporan los nombres de archivo .xaml).</span><span class="sxs-lookup"><span data-stu-id="3ccd3-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="3ccd3-134">Estos archivos intermedios pueden ayudarle a determinar el origen de determinadas construcciones de programación en las clases parciales combinadas en la aplicación compilada.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>  
  
 <span data-ttu-id="3ccd3-135">Controladores de eventos de la clase derivada deben ser `internal override` (`Friend Overrides` en Microsoft Visual Basic) con el fin de invalidar los códigos auxiliares para los controladores tal y como se crea en la clase intermedia durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="3ccd3-136">De lo contrario, las implementaciones de clase derivada ocultar la implementación de clase intermedia (instantáneas) y no se invocan los controladores de clase intermedia.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>  
  
 <span data-ttu-id="3ccd3-137">Cuando se definen conjuntamente `x:Class` y `x:Subclass`, no es necesario proporcionar ninguna implementación de la clase que hace referencia a `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="3ccd3-138">Solo debe asignarle un nombre a través de la `x:Class` de atributo para que el compilador tiene cierta orientación acerca de la clase que crea en los archivos intermedios (el compilador no selecciona un nombre predeterminado en este caso).</span><span class="sxs-lookup"><span data-stu-id="3ccd3-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="3ccd3-139">Puede asignar a la `x:Class` una implementación de la clase; sin embargo, esto no es el escenario típico para usar ambos `x:Class` y `x:Subclass`.</span><span class="sxs-lookup"><span data-stu-id="3ccd3-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccd3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ccd3-140">See Also</span></span>  
 [<span data-ttu-id="3ccd3-141">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="3ccd3-141">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="3ccd3-142">Clases XAML y personalizadas para WPF</span><span class="sxs-lookup"><span data-stu-id="3ccd3-142">XAML and Custom Classes for WPF</span></span>](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
